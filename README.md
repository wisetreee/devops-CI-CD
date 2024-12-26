# devops-CI-CD
Работу выполнил Ракитин Арсений, группа ИТХ-2-2021.
#
1. Создаём приложение и тесты.

   ![image](https://github.com/user-attachments/assets/6d36325a-b5a7-45b2-9620-fac3b674de7d)

2. Создаём ветку dev и устанавливаем правило, по которому пул реквест может осуществляться только после подтверждения.

   ![image](https://github.com/user-attachments/assets/631c8383-95cc-4672-a11c-92d6c09ced0c)

3. Сделаем коммит и отправим его в ветку dev, предварительно исправив функцию get_five() и отключив сигнатуры C0114, C0115, C0116.

   ![image](https://github.com/user-attachments/assets/8bb8d295-6fb2-4cca-b972-2e293a2bd314)

   ![image](https://github.com/user-attachments/assets/9201d790-36e5-440f-8c24-3467a84950f0)

   Тесты успешно пройдены, можно делать пул реквест.
   
4. Пробрасываем порт в vm.

   ![image](https://github.com/user-attachments/assets/b5fe97e8-03fb-4fe2-b853-0165c01a4a19)

5. Регистрируемся в докерхабе, создаем там репо и пишем манифест для куберизации приложения в /server-k8s-manifest/devops-psu.yml.
   В качестве образа указываем наш репо.
   
   ![image](https://github.com/user-attachments/assets/d0a563dc-7b63-4f6e-90b0-b2da06412718)

   ![image](https://github.com/user-attachments/assets/e9d8a5f2-5562-4308-9e18-e43e191a8555)

   
6. Запускаем minikube, создаем пространство имен devops-psu и в нем запускаем под, применяя манифест k8s.

   ![image](https://github.com/user-attachments/assets/c59fbe66-871c-4c94-ac97-76dd01a342a3)

   ![image](https://github.com/user-attachments/assets/dd0874db-bc85-4f98-b1c1-9f67510ae156)

   ![image](https://github.com/user-attachments/assets/b2a1abed-f1fb-413e-83db-52bcbb896b4f)

8. В докерхабе создаём токены доступа и закидываем их в гитхаб.

    ![image](https://github.com/user-attachments/assets/ea9f6e67-9ee6-4f24-bc68-f76df44596ef)

9. Пишем манифест для публикации образа в ветку release, а оттуда в докерхаб (файл .github/workflows/release.yml).
   Там же указываем наши токены, созданные ранее.

10. Публикуем все манифесты в гит.
    
11. Делаем коммит для проверки сценария. Образ опубликовался в докерхабе, а это значит, что наша задача выполнена!

    ![image](https://github.com/user-attachments/assets/c4ae9332-b8ac-4452-b723-a1af9feaa2f5)



