import requests
def getStr(string,start,end):
	str = string.split(start)
	str = str[1].split(end)
	return str[0]

def bicara(text):
    data = {
        'botcust2': '83abe01aaed12802',
        'message': text
    }
    req = requests.post("https://pandorabots.com/pandora/talk?botid=fd5c287f1e357db6&skin=talk", data=data)
    if req.status_code == 200:
        response_talk = getStr(req.text, 'var elizaresponse= "', '"')
        return "Riska: " + response_talk
while(True):
    word = input("Resky: ")
    reply = bicara(word)
    print(reply)
