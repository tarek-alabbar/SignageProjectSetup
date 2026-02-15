[![](https://mermaid.ink/img/pako:eNqlVdtu4jAQ_ZXIz7Qi3JO3FLIC7bJbFejDCqkyeBqsTezIdtpSyr93ciFAE9Turh8gnhmP55zjsXdkLRkQl4AacRooGi2FhWMx8--st7erK7mzRv79ZOhbriWfha66p_5o4qE3iUNJWU3AbDj2R4sfaYa1AmqgiCnyVqOo1jwQwOrC8tnD2Pfu5je-N8dwDeKwbZnkQ9KHydyfpvtLYSg_oMgrvxC6JIkGZnGxJHn0CbBd_p2OIOEYxKzb70ebNoqLwIKI8tBaVB0xAnyWio2p3hydDJkxPIKCJOaZ3Lc_3b4g45MCMhuWrybM-la3P0__h6h8XXkMnvgaFmmOGq-gERyNKylDoMLi-haTHiQ7gxNSbcZAlVkhrBr_STX-S4xJtGf-kpVcyP8j5ZGH8PMMG4gkyszzbQyV-FUoVwsVVuxmk0QrgcqfOUOJLs1fYSJutmUHpIMLY7FEUcOlmAEeUKZr0OfNdQF-eer_kYHMnqtez80lzb214U9VatKKX6WAz1X8gJFdVPi8O7-CU683wJIQ6rBGwDj94Mh04DoO6faXYqCOnqw4bfAEz_kpD5kd755z60meUSHrxT4-uca-AqlWopK-9AerjOJqv2MtoO5B6bKYMuc6UQqEmeaMVJby2GMMW1JXbzelpJqihwYF-j1pkEBxRlyjEmiQCBTegDglGbglMRtApkh6tzKq_qQXa7ompuK3lNFhmZJJsCHuIw01zvJDUbxNpRVLRomGMhGGuPag18myEHdHXojbcprXHafdGrSdftt2Bq0G2RLXca57dtPuN52u0-x2B919g7xm29rXrX633ez1bLvjdHqDZr9BkA6D8PK3MXsi9-91kSAs?type=png)](https://mermaid.live/edit#pako:eNqlVdtu4jAQ_ZXIz7Qi3JO3FLIC7bJbFejDCqkyeBqsTezIdtpSyr93ciFAE9Turh8gnhmP55zjsXdkLRkQl4AacRooGi2FhWMx8--st7erK7mzRv79ZOhbriWfha66p_5o4qE3iUNJWU3AbDj2R4sfaYa1AmqgiCnyVqOo1jwQwOrC8tnD2Pfu5je-N8dwDeKwbZnkQ9KHydyfpvtLYSg_oMgrvxC6JIkGZnGxJHn0CbBd_p2OIOEYxKzb70ebNoqLwIKI8tBaVB0xAnyWio2p3hydDJkxPIKCJOaZ3Lc_3b4g45MCMhuWrybM-la3P0__h6h8XXkMnvgaFmmOGq-gERyNKylDoMLi-haTHiQ7gxNSbcZAlVkhrBr_STX-S4xJtGf-kpVcyP8j5ZGH8PMMG4gkyszzbQyV-FUoVwsVVuxmk0QrgcqfOUOJLs1fYSJutmUHpIMLY7FEUcOlmAEeUKZr0OfNdQF-eer_kYHMnqtez80lzb214U9VatKKX6WAz1X8gJFdVPi8O7-CU683wJIQ6rBGwDj94Mh04DoO6faXYqCOnqw4bfAEz_kpD5kd755z60meUSHrxT4-uca-AqlWopK-9AerjOJqv2MtoO5B6bKYMuc6UQqEmeaMVJby2GMMW1JXbzelpJqihwYF-j1pkEBxRlyjEmiQCBTegDglGbglMRtApkh6tzKq_qQXa7ompuK3lNFhmZJJsCHuIw01zvJDUbxNpRVLRomGMhGGuPag18myEHdHXojbcprXHafdGrSdftt2Bq0G2RLXca57dtPuN52u0-x2B919g7xm29rXrX633ez1bLvjdHqDZr9BkA6D8PK3MXsi9-91kSAs)

**Mermaid code:**

```
erDiagram
    USER ||--o{ DEVICE : owns
    USER ||--o{ MEDIA : uploads
    USER ||--o{ SCHEDULE : creates
    DEVICE ||--o{ SCHEDULE : assigned
    DEVICE ||--o{ DEVICE_HEARTBEAT : sends
    SCHEDULE ||--o{ SCHEDULE_ITEM : contains
    MEDIA ||--o{ SCHEDULE_ITEM : "used in"

    USER {
        guid id PK
        string email UK
        string passwordHash
        datetime createdAt
    }

    DEVICE {
        guid id PK
        guid userId FK
        string pairingCode UK
        string deviceUuid UK
        string name
        boolean isPaired
        datetime lastHeartbeat
        datetime pairingCodeExpiresAt
        datetime createdAt
    }

    MEDIA {
        guid id PK
        guid userId FK
        string fileName
        enum fileType
        string blobUrl
        string thumbnailUrl
        long sizeInBytes
        int durationSeconds
        datetime uploadedAt
    }

    SCHEDULE {
        guid id PK
        guid userId FK
        guid deviceId FK
        string name
        boolean isActive
        string timezone
        datetime createdAt
        datetime updatedAt
    }

    SCHEDULE_ITEM {
        guid id PK
        guid scheduleId FK
        guid mediaId FK
        int displayOrder
        time startTime
        time endTime
        int displayDuration
    }

    DEVICE_HEARTBEAT {
        guid id PK
        guid deviceId FK
        datetime timestamp
        string playerVersion
        guid currentMediaId
        string ipAddress
        string errorMessage
    }
```
