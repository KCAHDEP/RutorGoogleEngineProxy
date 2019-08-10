Webproxy Rutor.org
========

Развертывание на Google App Engine
---------------------------------

Откройте [https://console.cloud.google.com/projectcreate](https://console.cloud.google.com/projectcreate) . Возможно, перед этим вам будет предложено войти в аккаунт Google.

На странице *New Project* введите название проекта и выберите свободный Project ID. Обратите внимание, в дальнейшем ваше приложение-прокси будет доступно по адресу http://{ваш_Project_ID}.appspot.com

Нажмите кнопку *Create*. Будет запущен процесс создания нового приложения. Дождитесь появления сообщения о успешном завершении в панели *Notifications* (справа, наверху).

![Notifications](http://images.vfl.ru/ii/1523011443/c77c1b79/21273759.png)

Рядом вы найдете кнопку *Activate Google Cloud Shell*. Нажмите ее.

![Activate Goole Cloud Shell](http://images.vfl.ru/ii/1523011521/427768bf/21273769.png)

В нижней части окна откроется черное окно консоли. Вставьте в нее следующую команду и нажмите ввод:

    git clone https://github.com/YouROK/RutorGoogleEngineProxy

Начнется копирование готового проекта в рабочую область. При успешном завершении в конце будет напечатана строка:
>Unpacking objects: 100% (/), done.

Чтобы приступить к развертыванию приложения на сервере выполните команду:

    gcloud app deploy RutorGoogleEngineProxy/app.yaml --version 1 --project ваш_Project_ID

Будет выведен список доступных площадок:

>Please choose the region where you want your App Engine application located:
>
> [1] europe-west2  (supports standard and flexible)
>
> [2] us-east1      (supports standard and flexible)
>
>  .. 
>
> [12] cancel
>
>Please enter your numeric choice:

Выберите сервер находящийся поближе к вам, или можете просто нажать "1" и клавишу ввода. 

Утилита установит соединение с указанной площадкой:

>Creating App Engine application in project [{ваш_Project_ID}] and region [us-central]....done.
>
> ..
>
>Do you want to continue (Y/n)?

Нажмите ввод еще раз чтобы выполнить развертывание.

После завершения ваше приложение сразу станет доступно по адресу https://{ваш_Project_ID}.appspot.com
