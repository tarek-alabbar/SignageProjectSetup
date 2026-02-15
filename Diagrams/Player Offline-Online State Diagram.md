[![](https://mermaid.ink/img/pako:eNqdVE2P2jAQ_SuWD3uoAJEATTaHXthWW6m7rRZxaenBOBNikdip40BZxH_fSZxss4HQqhyCZ_zemw-PfaRchUADmhtm4E6wjWbpcOeuJMHfj3c_yXD4gXyWwgiWiGchN3an7akg8xj4Fo1vTGj8C8gXxUISaZWSRHGWLIzSbAOWbb8dSiWzlBlaEAbkURGOC5BlnLyf8VUmQkJA7lneJpAbIqQBLcFc4UbRZfK6MESqjoL9NhlWArXYA_YwIItY7UlWy-coB9JSWqg3KTep5AXnkOdRkbQDWVRF-ASGx4hc8BjCIkHqE_wqIDcYxnospYuryHcizxJ2QPdcYT3SYKbNvgYOYofF3BDOSucVnddmPYLZK70loLXS7YzPIvXFf1LltBFeozLQnUIuKy1Ahui6B6bNGhgKfdyBPpAZSYUsDNRT0oX1ZfEHkKN9hfu_lTcjt8xCLDewNomUJhL2nYrfYntOvd5kOyYStr5CvVAt3qeiAvSS_l5mjegLsczLabaD9E8HehYxUbk5D9XclwalcfKVbob17LYsDpJXT1C5IPsYJFkzbLyqIPU5W0xPnysPSbAxrStGB3SjRUgDowsY0BR0ykqTHkvJFTUxpLCiAS5DprcrupIn5GRMflcqbWhaFZuYBhG-MmjZE6mf3VcIziDouSqkocFkNq00aHCkv9H0RtOx70wnjjOe-J7rD-iBBkN3Mpq5t7OJ63rj977n-acBfa6iOiPH81zPmU1vvbHv-VN3QCEU2L8H-_BX7__pBd-gBBY?type=png)](https://mermaid.live/edit#pako:eNqdVE2P2jAQ_SuWD3uoAJEATTaHXthWW6m7rRZxaenBOBNikdip40BZxH_fSZxss4HQqhyCZ_zemw-PfaRchUADmhtm4E6wjWbpcOeuJMHfj3c_yXD4gXyWwgiWiGchN3an7akg8xj4Fo1vTGj8C8gXxUISaZWSRHGWLIzSbAOWbb8dSiWzlBlaEAbkURGOC5BlnLyf8VUmQkJA7lneJpAbIqQBLcFc4UbRZfK6MESqjoL9NhlWArXYA_YwIItY7UlWy-coB9JSWqg3KTep5AXnkOdRkbQDWVRF-ASGx4hc8BjCIkHqE_wqIDcYxnospYuryHcizxJ2QPdcYT3SYKbNvgYOYofF3BDOSucVnddmPYLZK70loLXS7YzPIvXFf1LltBFeozLQnUIuKy1Ahui6B6bNGhgKfdyBPpAZSYUsDNRT0oX1ZfEHkKN9hfu_lTcjt8xCLDewNomUJhL2nYrfYntOvd5kOyYStr5CvVAt3qeiAvSS_l5mjegLsczLabaD9E8HehYxUbk5D9XclwalcfKVbob17LYsDpJXT1C5IPsYJFkzbLyqIPU5W0xPnysPSbAxrStGB3SjRUgDowsY0BR0ykqTHkvJFTUxpLCiAS5DprcrupIn5GRMflcqbWhaFZuYBhG-MmjZE6mf3VcIziDouSqkocFkNq00aHCkv9H0RtOx70wnjjOe-J7rD-iBBkN3Mpq5t7OJ63rj977n-acBfa6iOiPH81zPmU1vvbHv-VN3QCEU2L8H-_BX7__pBd-gBBY)

**Mermaid code:\***

```
stateDiagram-v2
    [*] --> Initializing
    Initializing --> CheckingPairing: Load from localStorage

    CheckingPairing --> Unpaired: No credentials
    CheckingPairing --> Online: Has credentials & internet
    CheckingPairing --> Offline: Has credentials but no internet

    Unpaired --> PairingMode: Show pairing screen
    PairingMode --> Online: Pairing successful

    Online --> FetchingSchedule: Request schedule
    FetchingSchedule --> DisplayingContent: Schedule received & cached
    FetchingSchedule --> Offline: Network error

    DisplayingContent --> DisplayingContent: Rotate content per schedule
    DisplayingContent --> SendingHeartbeat: Every 5 minutes
    SendingHeartbeat --> DisplayingContent: Heartbeat sent
    SendingHeartbeat --> Offline: Network error

    DisplayingContent --> CheckingUpdate: Check for new schedule
    CheckingUpdate --> FetchingSchedule: Update available
    CheckingUpdate --> DisplayingContent: No update
    CheckingUpdate --> Offline: Network error

    Offline --> DisplayingContent: Using cached schedule
    DisplayingContent --> Offline: Network lost
    Offline --> Online: Network restored

    Online --> Syncing: Sync when back online
    Syncing --> FetchingSchedule: Fetch latest schedule
```
