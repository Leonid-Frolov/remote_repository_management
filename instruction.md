# КАК РАБОТАТЬ С УДАЛЕННЫМ РЕПОЗИТОРИЕМ GIT 


Напомним, что GIT - это распределенная система управления версиями, позволяющая отслеживать изменения в коде и сотрудничать над проектами. Ветвление и слияние - одна из самых мощных возможностей GIT, которая позволяет разработчикам эффективно вносить изменения в код и интегрировать их в основную ветку. Однако работа с удалёнными репозиториями - это совсем другая история. 

Удалённый репозиторий -  это репозиторий, расположенный на каком - то сервере в сети. Он позволяет команде разработчиков сотрудничать над кодом и избегать проблем, связанных с одновременными изменениями. 

Работа с удаленными репозиториями в GIT включает в себя операции клонирования, загрузки, отправки, слияния и удаления. 

Во время работы с удалёнными репозиториями разработчики могут синхронизировать код и обмениваться изменениями, что позволяет им легко отслеживать историю изменений и решать возникающие конфликты. 

Важно разобраться в том, как создавать и настравать удаленные репозитории, а также правильно использовать операции синхронизации, чтобы избежать возможных ошибок и проблем при работе в команде.  


#### Подготовка к работе 


Перед началом работы с удаленными репозиториями в GIT необходимо выполнить несколько подготовительных шагов. 

Во-первых, убедитесь, что у вас установлен GIT на вашем компьютере. Если установлен, то убедитесь, что работаете с последней версией. 

Вам потребуется создать учетную запись на платформе и настроить связь  GIT  с вашим аккаунтом. Для этого необходимо исполнить команды:  


````

Git config –global user.name <Ваше имя> 

Git config – global user.email<Ваш email> 

Git config –global user.telephon<Ваш телефон> 

`````

Рекомендуется сгенерировать SSH-ключ бля безопасной аутентификации на удаленном сервере. Это позволит вам подключаться к удаленным репозиториям без ввода пароля каждый раз. Для создания SSH-ключа выполните команду: 


````

SSH-keygtn-t rsa –b 4096 –c <Ваш email> 

````


После генерации ключа вам потребуется добавить его в свой профиль на платформе для хостинга репозитория. 

После завершения этих шагов вы будете готовы к работе с удаленными репозиториями в GIT. Вы сможете клонировать удаленные репозитории на ваш ПК, вносить изменения и отправлять их обратно на удаленный сервер. Это удобный и надежный способ совместной работы над проектами и широко используется в различных областях разработки программного обеспечения. 

# Создание удаленного репозитория 

Создание удаленного репозитория в GIT позволяет вам хранить свой код на удаленном сервере и обмениваться им с другими разработчиками. Это особенно полезно, когда вы работаете в команде, или хотите иметь резервную копию своего кода. 

Если у вас уже есть локальный репозиторий, вы можете связать его с удаленным репозиторием. В противном случае вы можете создать новый удаленный репозиторий на платформе размещения кода, такой как GITHUB. 

Для создания удаленного репозитория на платформе размещения кода вам может потребоваться создание учетной записи и войти в свой аккаунт.  

Затем вы можете создать новый репозиторий, указав его имя и описание. Многие платформы также позволяют вам настроить различные параметры и разрешения доступа к вашему репозиторию. 

После создание удаленного репозитория, вы получите URL - адрес, который можете использовать для связи с вашим локальным репозиторием. Для этого вам следует исполнить команду: 

````

Git remote add origin [URL] 

````

Здесь origin - это просто имя, которое вы выбираете для вашего удаленного репозитория. После связывания локального и удаленного репозитория вы можете отправить свои изменения на удаленный репозиторий. Это выполняется исполнением команды: 

````

Git push 

````

Кроме того, вы можете синхронизировать ваш локальный репозиторий с удаленным репозиторием, исполняя команду: 

````

Git pull 

````

Создание удаленного репозитория в git - это простой и важный шаг в управлении вашим кодом и сотрудничестве с другими разработчиками. Следуя этим шагам, вы можете эффективно с удаленными репозиториями и иметь контроль над своим кодом в любое время. 


# Клонирование (скачивание) удаленного репозитория 


Для клонирования удаленного репозитория вам понадобится URL-адрес удаленного репозитория. Обычно этот адрес предоставляется вам владельцем репозитория или сервисом хостинга GIT, таким как GITHUB, GITLAB.  

Чтобы клонировать удаленный репозиторий следует исполнить команду: 

````

GIT clone<URL - адрес удаленного репозитория> 

````

Вам необходимо указать URL адрес удаленного репозитория в качестве аргумента команды. 

После выполнения этой команды GIT создает новую папку с именем удаленного репозитория и скачивает все файлы и историю изменений из удаленного репозитория в эту папку. Клонирование не только загружает файлы из удаленного репозитория, но и создает соответствующий локальный репозиторий с историей изменений, коммитами и настройками веток. 

Клонирование удаленного репозитория очень полезно при совместной работе в команде. Оно позволяет каждому члену команды получить актуальную версию проекта и легко делать изменения, не влияя на работу других участников. Более того, каждый участник может работать в своей  личной ветке, что предотвращает конфликты при объединении изменений. 

# Работа с удаленными ветками 


Чтобы создать удаленную ветку, необходимо выполнить команду git push с указанием имени ветки и удаленного репозитория. 

````

Git push origin <имя ветки> 

````

После этого ветка будет создана на удаленном репозитории и будет доступна для других разработчиков. 

Чтобы переключиться на удаленную ветку, необходимо выполнить команду git chtckout  с указанием имени ветки. 


````

 git chtckout  с указанием имени ветки. 

 ````

 Если вам больше не нужна удаленная ветка, вы можете её удалить с помощью команды git push с указанием флага --delete и имени ветки. 


 ````

 Git push origin –delete <имя ветки> 

 ````

 Таким образом, вы сможете легко управлять удаленными ветками в git и совместно работать с другими разработчиками над проектом. 


 # Работа с локальными ветками и удаленным репозиторием 


 Для работы с удаленными репозиториями в git вам необходимо использовать локальные ветки. Ветка - это параллельная линия разработки, которая позволяет вам работать над определенным функционалом отдельно от основной ветки проекта. 

Чтобы создать новую локальную ветку исполняйте команду: git branch <имя ветки>. Затем вы сможете переключиться  на созданную ветку с помощью исполнения команды: git checkout <имя ветки>. 

После создания локальной ветки и внесения в неё изменени	, вы можете отправить изменения на удаленный репозиторий. Для этого выполняется команда: 


````

Git push <имя удаленного репозитория><имя ветки> 

````

Эта команда загрузит все ваши изменения на удаленный сервер и создаст новую ветку с таким же именем в удаленном репозитории. 
Если вы хотите обновить свою локальную ветку данными из удаленного репозитория, используйте исполнение команды: 

````

Git pull <имя_удаленного_репозитория><имя_ветки> 

````


Эта команда загрузит последние изменения из удаленного репозитория и объединит их с вашей локальной веткой. 

Важно отметить, что перед отправкой изменений на удаленный репозиторий или получением изменений (обновлений) из него, рекомендуется убедиться, что ваша локальная ветка находится в актуальном состоянии. Это достигается исполнением команды git status, которая покажет текущий статус вашей ветки и наличие неотправленных или не обновленных изменений. 

Работа с локальными ветками и удаленными репозиториями являются основной частью работы с git. Правильное использование веток позволяет разработчикам эффективно сотрудничать, вносить изменения в проект и контролировать версии кода. 


# Добавление изменений в удаленный репозиторий 

Сначала убедитесь, что ваш локальный репозиторий содержит все нужные изменения 

Затем убедитесь, что вы находитесь в ветке, в которой хотите отправить изменения 

Исполнить команду git push с указанием удаленного репозитория и ветки, куда вы хотите отправить изменения. 

````

Git push origin masner

````

GIT отправит все коммиты, которых нет в удаленном репозитории и обновит его содержимое. Если вы работаете с общим репозиторием, возможно, вам потребуется ввести свои учетные данные для доступа. 

Помимо команды git push есть и другие варианты передачи изменений в удаленный репозиторий. 

Git push --force - Принудительно добавляет изменения, даже если они противоречат истории репозитория. 

Git push --tags - Отправляет только метки (теги) на удаленный репозиторий. 

При исполнении команды git push будьте осторожны, чтобы не перезаписать чужие изменения или не отправить ненужные файлы или конфиденциальную информацию. 

Регулярно проверяйте состояние своего репозитория и обновленные версии удаленного репозитория. 

Добавление изменений в удаленный репозиторий - важный шаг в работе с git, который позволяет совместно работать над проектами и обмениваться обновлениями с другими разработчиками. 

# Получение изменений из удаленного репозитория 


Исполнение команды git pull обновляет локальный репозиторий и объединяет изменения из удаленного репозитория с текущей веткой. 

Чтобы исполнить команду git pull следует находиться в рабочем каталоге репозитория и быть подключенным к удаленному репозиторию. 

Также можно указать имя удаленного репозитория и ветку, из которой нужно получить изменения.  Это выполняется при помощи команды: 

Git pull origin <имя ветки> 

Например, чтобы получить изменения из ветки  develop удаленного репозитория origin нужно исполнить команду: 

Git pull origin develop 

 Git pull - Обновляет локальный репозиторий и объединяет изменения с текущей веткой. 

Git pull origin <имя ветки> - Получает изменения из указанной ветки удаленного репозитория. 

Получение изменений из удаленного репозитория, является необходимым шагом при работе с командой и позволяет быть в актуальном состоянии проекта. 


# Настройка удаленного репозитория для вилки 

Одной из ключевых функций GITHUB является возможность создания веток, так называемых “вилок”, для дальнейшей независимой работы над проектами. 

Если вы хотите внести свои изменения в существующий проект, но не имея права прямого доступа к его репозиторию, создание вилки станет наилучшим решением. 

Настройка удаленного репозитория для вилки является важным шагом в процессе работы с GITHUB. В этом руководстве разберемся  и освоим как создать вилку и настроить удаленный репозиторий для вашего проекта, а также дадим рекомендации для эффективной работы. 


# Настройка удаленного репозитория для вилки на GITHUB. 

Чтобы создать удаленный репозиторий для вилки на github, следуйте следующим шагам: 

Откройте страницу репозитория, который вы хотите форкнуть 

Нажмите на кнопку “FORK” в правом верхнем углу страницы. Это создаст копию репозитория в вашем аккаунте. 

После того как форк будет завершен, перейдите на страницу нового репозитория в вашем аккаунте. 

Скопируйте URL-адрес репозитория, нажав на кнопку “CLONE OR DOWNLOAD” и копируйте URL-адрес из поля 

Откройте командную строку или терминал на вашем ПК 

Введите команду git clone и вставьте url-адрес репозитория после неё. Запустите клонирование и подождите пока оно завершится 

Теперь у вас есть локальная копия удаленного репозитория на вашем ПК 

Если вы хотите внести изменения в вилку и предложить изменения в оригинальный репозиторий, создайте новую ветку с помощью команды git branch. Внесите изменения и сохраните их 

Затем используя команду git push исполните отправку изменений  в удаленный репозиторий на github. 

В окне на GITHUB появится возможность отправить PULL REQUEST 

Теперь у вас есть удаленный репозиторий для вилки на github, с которым вы можете работать и делиться своими изменениями. 