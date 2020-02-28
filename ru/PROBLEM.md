## Мини-информационная панель {: # мини-информационная панель}

<figure class="attempt-right"><img class="screenshot" src="/web/updates/images/2018/06/a2hs-infobar-cropped.png"><figcaption> Мини-инфобар </figcaption></figure>

**Мини-информационная панель - это промежуточный опыт для Chrome на Android,** поскольку мы работаем над созданием согласованного интерфейса для всех платформ, который включает кнопку установки в омнибоксе.

Мини-информационная панель является компонентом пользовательского интерфейса Chrome и не контролируется сайтом, но может быть легко отклонена пользователем. После удаления пользователем он не появится снова, пока не пройдет достаточное количество времени (в настоящее время 3 месяца). Мини-информационная панель будет отображаться, когда сайт соответствует [критериям](#criteria) , независимо от того, `preventDefault()` ли вы `preventDefault()` в событии `beforeinstallprompt` или нет.

Примечание. Мини-информационная панель не отображается на настольных устройствах.