Welcome to hodl-net's documentation!
------------------------------------

HODL-NET - распределённая зашифрованная анонимная самоорганизовывающаяся сеть поверх сети Интернет.
Основной упор в реализации направлен на анонимность. Это достигается путём индификации пользователей
исключительно по слепку публичного ключа, системы туннелирования и постоянной генерации "мусорных" сообщений.

--------


Принцип работы
--------------

При запуске происходит соединение с узлами сети. Адреса этих узлов можно задать вручную, но по-умолчанию
адреса берутся из базы данных (если она присутствует). После подключения происходит синхронизация базы данных,
выполняется директива `hodl_net.server.Server.on_open`.

Любое сообщение для сохранения анонимности отсылается через туннель. Туннель создаётся рандомно, путём пересылания
сообщения между соседними узлами. Если какой-то из узлов оказывается скомпрометирован и получает сообщение от
другого узла, то определить, является ли этот узел отправителем или всего лишь пересылает сообщение, затруднительно.
По достижению конца туннеля, сообщение рассылается по всей сети. Если у сообщения есть конкретный получатель, то
оно отправляется в зашифрованном виде со слепком публичного ключа.

.. toctree::
   :maxdepth: 3
   :glob:
   :hidden:

   src/*