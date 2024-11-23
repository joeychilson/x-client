# xclient

A Python client for the public X API.

Note: This should be used for personal use only. It's very unreliable due to X blocking requests often.

## Example

```python
import asyncio

from xclient.client import XAPIError, XClient


async def main():
    async with XClient(
        auth_token="",
        api_token="",
        csrf_token="",
        client_transaction_id="",
    ) as client:
        try:
            create_tweet = await client.create_tweet(text="Hello, world!")
            print(create_tweet)
        except XAPIError as e:
            print(f"Error: {e}")
        except Exception as e:
            print(f"Unexpected error: {e}")


if __name__ == "__main__":
    asyncio.run(main())
```