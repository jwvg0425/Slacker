SlackAPI
====

�޼��� �����ϱ�
----
```cs
Slack.SendMessage("CHANNEL_ID", "MESSAGE_TO_SEND");
```

�̹��� �����ϱ�
----
```cs
Slack.SendImage("CHANNEL_ID", "IMAGE_URL");

Slack.SendImage("CHANNEL_ID", "IMAGE_URL", "TITLE (OPTIONAL)");
```

���� �����ϱ�
----
```cs
Slack.SetAway();

Slack.SetActive();
```

Auth ��ū ��������
----
```cs
var authToken = Slack.me.authToken;
```