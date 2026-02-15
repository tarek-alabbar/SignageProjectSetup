[![](https://mermaid.ink/img/pako:eNp9Vm1TGjEQ_iuZ9Es7Q5VDQGCsHQVRZ9Q6RdtpTz-EuwUyhguTy4n09L832dyrqNwMZDfPbnb32eyR0kCGQAd0JuQ6WDClyc3oLiLmM9FG-uxfC7YB5aT4_gv5-vWQDBcQPFwzriBMR_DIAziYqt1Dp_n-4uzddwVqTZ-v5DOZLOTaqng09-2aZAKZBAogus_OL1F46EmkQQ1NtP5tbAJCMSZWkRkUABcjE-Io0PyRafCvf0xuyC5b8d0VprPLsp3MtApG64mWCoYm6NjHJbFriDRnIs7jKyCva_JR_n8gfiZj0MFiEiwgTAT4pyf12OJsIzunBsajzlicy2m-QAKOHhkXbCqgzkEFX-NgBDOWCO04yISMA3R3IeeSSEWOBQseKqzkUBvLb8a159tv0iFLHiUa8gLhFoJqKXwUGVYHSzZkRp9eQsgZxoJy0VslpEhoJNeRkCxEEz-XyEzJpUlATpEvNs-rWoNnDWPcXciACd955hE5j0J4gnB0XPRJjik5R90W5WVwmNMp6GGilOmgG740lIMmmUysInNfR7nScWG6GnsTfCcQJ5FzDcsYixPby4kmB99IZMg0PxCFFc9VN3kPOSnd8jaWSRRudVBp-7p_3gfmqV_Bk8ac7QJPssX9KTXTXEZl8rhdFPZms8o6gNjlG3PFqvGg86Vh1vQAj-0dQsnPBIISGSdCxNXxUnfwi4cgCwco4eQjuNy2zpqocl5xG0aJwrTcpcijyLX3NUvn_bVl9Yiq3k0mQ-wZGL6nwHSKdw5ZA8FWcXlDarCSjEK1PRIX-VYWYs3alet2FZoBmV7Bmnw8d7ZPtz1T8bFFpVO_MyLfxlmX9RtT9RrrjRkq-NoiMy7E4FN7eDTuNGu7lVeMw4zHQ6-5X8XUOHagltfvjvfeADk63wNVR6fD9E_sQxt0rnhIB1ol0KBLUEtmRZpa6zuqF2BSowOzDJl6uKN30YuxWbHor5TL3EzJZL6gg5l5QRkpwTKNOJsrVkIMK_YNmUSaDry97j46oYOUPhm5t7fTaXnNdq_Xapqn323QDR10mzv9bs9rNdtdr9_pdtvtlwb9h-e2drx-v-W1e_221241zVaDmttqxuyl-0-Bfy1e_gMd_cbg?type=png)](https://mermaid.live/edit#pako:eNp9Vm1TGjEQ_iuZ9Es7Q5VDQGCsHQVRZ9Q6RdtpTz-EuwUyhguTy4n09L832dyrqNwMZDfPbnb32eyR0kCGQAd0JuQ6WDClyc3oLiLmM9FG-uxfC7YB5aT4_gv5-vWQDBcQPFwzriBMR_DIAziYqt1Dp_n-4uzddwVqTZ-v5DOZLOTaqng09-2aZAKZBAogus_OL1F46EmkQQ1NtP5tbAJCMSZWkRkUABcjE-Io0PyRafCvf0xuyC5b8d0VprPLsp3MtApG64mWCoYm6NjHJbFriDRnIs7jKyCva_JR_n8gfiZj0MFiEiwgTAT4pyf12OJsIzunBsajzlicy2m-QAKOHhkXbCqgzkEFX-NgBDOWCO04yISMA3R3IeeSSEWOBQseKqzkUBvLb8a159tv0iFLHiUa8gLhFoJqKXwUGVYHSzZkRp9eQsgZxoJy0VslpEhoJNeRkCxEEz-XyEzJpUlATpEvNs-rWoNnDWPcXciACd955hE5j0J4gnB0XPRJjik5R90W5WVwmNMp6GGilOmgG740lIMmmUysInNfR7nScWG6GnsTfCcQJ5FzDcsYixPby4kmB99IZMg0PxCFFc9VN3kPOSnd8jaWSRRudVBp-7p_3gfmqV_Bk8ac7QJPssX9KTXTXEZl8rhdFPZms8o6gNjlG3PFqvGg86Vh1vQAj-0dQsnPBIISGSdCxNXxUnfwi4cgCwco4eQjuNy2zpqocl5xG0aJwrTcpcijyLX3NUvn_bVl9Yiq3k0mQ-wZGL6nwHSKdw5ZA8FWcXlDarCSjEK1PRIX-VYWYs3alet2FZoBmV7Bmnw8d7ZPtz1T8bFFpVO_MyLfxlmX9RtT9RrrjRkq-NoiMy7E4FN7eDTuNGu7lVeMw4zHQ6-5X8XUOHagltfvjvfeADk63wNVR6fD9E_sQxt0rnhIB1ol0KBLUEtmRZpa6zuqF2BSowOzDJl6uKN30YuxWbHor5TL3EzJZL6gg5l5QRkpwTKNOJsrVkIMK_YNmUSaDry97j46oYOUPhm5t7fTaXnNdq_Xapqn323QDR10mzv9bs9rNdtdr9_pdtvtlwb9h-e2drx-v-W1e_221241zVaDmttqxuyl-0-Bfy1e_gMd_cbg)

**Mermaid code:**

```
flowchart TD
    Start([Player Starts]) --> CheckPaired{Device<br/>Paired?}

    CheckPaired -->|No| ShowPairing[Show Pairing Screen]
    ShowPairing --> EnterCode[User Enters Code]
    EnterCode --> CallActivate[POST /api/player/activate]
    CallActivate --> StoreCreds[Store Credentials]
    StoreCreds --> CheckPaired

    CheckPaired -->|Yes| FetchSchedule[GET /api/player/schedule]
    FetchSchedule --> HasSchedule{Schedule<br/>Available?}

    HasSchedule -->|No| ShowDefault[Show Default Screen<br/>Logo or Black]
    ShowDefault --> Wait1[Wait 5 minutes]
    Wait1 --> FetchSchedule

    HasSchedule -->|Yes| CheckCache{Media<br/>Cached?}
    CheckCache -->|No| DownloadMedia[Download from Blob Storage]
    DownloadMedia --> CacheLocal[Cache in IndexedDB]
    CacheLocal --> CheckCache

    CheckCache -->|Yes| GetCurrentTime[Get Current Time]
    GetCurrentTime --> FilterActive[Filter Active Items<br/>startTime <= now <= endTime]
    FilterActive --> HasActive{Active Items<br/>Found?}

    HasActive -->|No| ShowDefault

    HasActive -->|Yes| GetNext[Get Next Item in Rotation]
    GetNext --> CheckType{Media Type?}

    CheckType -->|Image| DisplayImage[Display Image Fullscreen]
    CheckType -->|Video| DisplayVideo[Play Video Fullscreen]

    DisplayImage --> WaitDuration[Wait Display Duration]
    DisplayVideo --> WaitDuration

    WaitDuration --> SendHeartbeat{5 min<br/>elapsed?}
    SendHeartbeat -->|Yes| Heartbeat[POST /api/player/heartbeat]
    Heartbeat --> CheckUpdate{New Schedule<br/>Available?}
    SendHeartbeat -->|No| CheckUpdate

    CheckUpdate -->|Yes| FetchSchedule
    CheckUpdate -->|No| GetCurrentTime

    style Start fill:#4CAF50
    style ShowPairing fill:#FFC107
    style DisplayImage fill:#2196F3
    style DisplayVideo fill:#2196F3
    style ShowDefault fill:#9E9E9E
```
