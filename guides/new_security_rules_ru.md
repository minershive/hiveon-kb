---
title: Новые правила безопасности Hive OS
parent_category: Гайды
path: /guides-new_security_rules_ru
lang: ru
parent_category_path: /guides_ru
order: 1
meta_description: Hive OS стала еще более безопасной. Ознакомьтесь с этой статьей и узнайте все о новых правилах.
---

Благодаря последним обновлениям, Hive OS стала еще более безопасной — теперь для выполнения некоторых действий будет необходим код подтверждения. Подробности ниже:
### Для новых пользователей
- Новые пользователи обязательно должны подтверждать свой email-адрес при регистрации.

- При необходимости код можно будет переотправить (первый раз он отправляется автоматически после нажатия на кнопку Register).

<img src="https://lbd.hiveos.farm/kb/images/security1.png" alt="securityrulesofhiveos">


<img src="https://lbd.hiveos.farm/kb/images/security2.png" alt="securityrulesofhiveos">

- При первом входе в аккаунт, нового пользователя встретит окно, где можно будет включить 2ФА (плюс видео-гайд).

### Смена email
- Пока ваш email-адрес не подтвержден, вы можете сменить его без кода подтверждения.

- Если ваш email-адрес уже подтвержден, но при этом у вас не включена 2ФА, код подтверждения будет отправлен на текущую почту, а при следующем шаге — уже на новую.

- Если же ваш email-адрес подтвержден, и при этом у вас включена 2ФА, сначала будет запрошен код с 2ФА, а потом — код с нового email-адреса.

### Действия, защищенные кодом подтверждения с почты (если не включена 2ФА)
- Смена пароля внутри аккаунта.

- Просмотр и создание API токенов.

<img src="https://lbd.hiveos.farm/kb/images/security3.png" alt="securityrulesofhiveos">

- Открытие доступа к ферме другим пользователям.

<img src="https://lbd.hiveos.farm/kb/images/security4.png" alt="securityrulesofhiveos">

- Отправка средств с вашего баланса Hive OS другому пользователю.

- Передача фермы другому пользователю.

- Пополнение чужой фермы с баланса аккаунта или с одной из ваших ферм (данное действие нужно подтверждать один раз, далее ферма становится доверенной, и следующие пополнения не будут требовать кода подтверждения).

- Подписка или отписка от уведомлений в Telegram, Discord.

- Уведомление о входе в аккаунт.

- Создание белого списка IP адресов, с которых можно войти в аккаунт.

- Включение 2ФА.

### Дополнительная информация
- Пока email-адрес не подтвержден, в настройках будет сообщение об этом. После подтверждения статус сменится на Your email is confirmed.

<img src="https://lbd.hiveos.farm/kb/images/security5.png" alt="securityrulesofhiveos">

<img src="https://lbd.hiveos.farm/kb/images/security6.png" alt="securityrulesofhiveos">

- Если подтвержден email-адрес и включена 2ФА, код подтверждения будет запрошен в 2ФА. Если подтвержден только email-адрес, код будет запрошен с почты.

**Мы настоятельно рекомендуем вам включить 2ФА, чтобы сделать ваш аккаунт более защищенным!** 🔐🛡

В случае возникновения каких-либо вопросов или трудностей, не стесняйтесь обращаться к нам — bee@hiveos.farm. Мы всегда готовы помочь.
