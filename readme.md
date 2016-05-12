Slacker
====

![slack](slack.png)

Make Your OWN Bot.

��ū ��������
----
__https://api.slack.com/docs/oauth-test-tokens__
<br>
�� ���丮�� `token` ������ ����� ������ ��ū�� �ְ� �����մϴ�.

��ɾ� �߰��ϱ�
----
`plugins/` ���� �Ʒ��� `.csx` ������ ������ �� �Ʒ��� ���� �Է��մϴ�.
```cs
using System;
using Slacker.Exports;

[Subscribe("�ȳ�")]
public void OnHello(Message msg) {
  Slack.SendMessage(msg.channel, "�ȳ� " + msg.sender);
}
```

���� `.csx` ������ �����ϸ� ���� �ڵ����� ��������� �� �ε��մϴ�.


ĸó ����ϱ�
----
```cs
// ���Խ� ĸó
[Subscribe("^������\\s(.+)$")]
public void Echo(Message msg){
	Slack.SendMessage(msg.channel, msg.matchData.Groups[1].Value);
}
```


Message ����ü
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