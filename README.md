# twitter-bot
# its a twitter bot for twitter analytics
import tweepy as tw


consumer_key = ""
consumer_secret = ""
access_token = ""
access_token_secret = ""

auth = tw.OAuthHandler(consumer_key , consumer_secret)
auth.set_access_token(access_token , access_token_secret)
api = tw.API(auth)

user = api.verify_credentials()

print("User DETAILS are : ")
print(user.name)
print(user.screen_name)
print(user.followers_count)

def limit_handled(cursor):
    while true:
        try:
            yield cursor.next()
        except tw.RateLimitError:
            time.sleep(10)
        except StopIteration:
            time.sleep(10)

for friend in user.friend():
   print(friend.name)
for follower in tw.Cursor(api.followers).items():
    if followers.friends.count < 300:
        print(follower.screen_name)
