# Moved to https://codeberg.org/icewind/ugc-scaper

# ugc-scraper

_We have ugc api at home_

## Usage

```rust
use ugc_scraper::{Result, SteamID, UgcClient};

#[tokio::main]
async fn main() -> Result<()> {
    let client = UgcClient::new();
    let id = SteamID::from(76561198024494988);
    let player = client.player(id).await?;
    println!("{}", player.name);
    for team in player.teams {
        println!(
            "  {} playing {} since {}",
            team.team.name, team.league, team.since
        )
    }

    Ok(())
}
```
