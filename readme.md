Slacker
====

![slack](slack.png)

Make Your OWN Bot.

Screenshot
----
![bot](bot.png)

토큰 가져오기
----
__https://api.slack.com/docs/oauth-test-tokens__
<br>
봇 디렉토리에 `token` 파일을 만들고 가져온 토큰을 넣고 저장합니다.

명령어 추가하기
----
`plugins/` 폴더 아래에 `.csx` 파일을 생성한 후 아래와 같이 입력합니다.
```cs
using System;
using Slacker.Exports;

[Subscribe("안녕")]
public void OnHello(Message msg) {
  Slack.SendMessage(msg.channel, "안녕 " + msg.sender);
}
```

이후 `.csx` 파일을 수정하면 봇이 자동으로 변경사항을 재 로드합니다.


캡처 사용하기
----
```cs
// 정규식 캡처
[Subscribe("^따라해\\s(.+)$")]
public void OnEcho(Message msg){
	Slack.SendMessage(msg.channel, msg.matchData.Groups[1].Value);
}
```


Message 구조체
----
```cs
public class Message {
  public string sender { get; set; }
  public string channel { get; set; }
  public string message { get; set; }
  
  // System.Text.RegularExpressions
  public Match matchData { get; set; }
}
```

Slack API
----
__내 프로필 가져오기__
```cs
var me = Slack.me;

string id = me.id;
string name = me.name;
bool isBot = me.isBot;
string email = me.email;
```

__메세지 보내기__
```cs
Slack.SendMessage("CHANNEL_NAME", "MESSAGE");
```

__상태 변경하기__
```cs
Slack.SetActive();
Slack.SetAway();
```

__채널__
```cs
var joinned = Slack.joinnedChannels;

var all = Slack.channels;
```
