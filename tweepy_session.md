```
import tweepy

def get_api(cfg):
  auth = tweepy.OAuthHandler(cfg['consumer_key'], cfg['consumer_secret'])
  auth.set_access_token(cfg['access_token'], cfg['access_token_secret'])
  return tweepy.API(auth)
def main():
   # Fill in the values noted in previous step here
   cfg = {  "consumer_key"        : "value",  "consumer_secret"     : "value","access_token"        : "value",  "access_token_secret" : "value"  }
   api = get_api(cfg)
   status = api.update_status(status='Good evening Guys') 
   # Yes, tweet is called 'status' rather confusing

 
if __name__ == "__main__":
  cfg=main()
```
