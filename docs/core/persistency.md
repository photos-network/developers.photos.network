# Persistency

Files are just written in the *data/files/* directory. 

```shell
data/
└── files/
    └── A1B2C3D4-E5F6-A1B2-C3D4-A1B2C3D4E5F6
        └── 2023
            ├── DSC_1234.xmp
            ├── DSC_1234.jpg
            ├── DSC_1234.NEW
            ├── DSC_1234.dng
            └── DSC_1234_overlay.jpg
```

Metadata are saved in a relational like **SQLite** or **PostgreSQL** and split into several tables.

``` mermaid
erDiagram
    USER {
        uuid uuid
        string email
        string password
        string lastname
        string firstname
        bool is_locked
        timestampz created_at
        timestampz updated_at
        timestampz last_login_at
    }
    MEDIA {
        uuid uuid
        uuid owner
        string name
        bool is_sensitive
        timestampz added_at
        timestampz taken_at
    }
    MEDIA }|--|| USER : owner
    REFERENCE {
        uuid uuid
        uuid media
        uuid owner
        uuid details
        string filepath
        string filename
        integer size
        string description
        timestampz last_modified
    }
    REFERENCE ||--|| MEDIA : media
    REFERENCE ||--|| USER : owner
    REFERENCE ||--|| DETAILS : details
    DETAILS {
        uuid uuid
        string camera_manufacturer
        string camera_model
        string camera_serial
        string lens_model
        string lens_serial
        string orientation
        string compression
        float resolution_x
        float resolution_y
        string resolution_unit
        float exposure_time
        string exposure_mode
        string exposure_program
        string exposure_bias
        float aperture
        long focal_length 
        int iso
        string color_space
        long pixel_x
        long pixel_y
        string user_comment
        string white_balance
        bool flash
        float exif_version
    }
    TAGS {
        uuid uuid
        uuid media
        string tag
        string origin
    }
    TAGS ||--|{ MEDIA : media
    LOCATIONS ||--|{ MEDIA : media
    LOCATIONS {
        uuid uuid
        uuid media
        float latitude
        float longitude
        float altitude
    }
```

These data are merged in regarding repositories.
