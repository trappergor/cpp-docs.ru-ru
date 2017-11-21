---
title: "Шаг 0 - поддержка Установка C++ в Visual Studio | Документы Microsoft"
description: "Установить поддержку Visual C++ в Visual Studio"
ms.custom: mvc
ms.date: 10/17/2017
ms.topic: get-started-article
ms.technology: devlang-C++
ms.devlang: C++
dev_langs: C++
ms.assetid: 45138d70-719d-42dc-90d7-1d0ca31a2f54
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 840f23d894e8aacc53a735fa8e1c25a671ed3a2a
ms.sourcegitcommit: 69632887f7a85f4841c49b4c1353d3144927a52c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/11/2017
---
# <a name="install-c-support-in-visual-studio"></a>Установка поддержки C++ в Visual Studio

Если это еще не загружен и установлен Visual Studio и инструментов Visual C++, вот как можно приступить к работе.

## <a name="prerequisites"></a>Предварительные требования

- Высокоскоростное подключение к Интернету. Установщик Visual Studio можно загрузить несколько гигабайт данных.

- На компьютере под управлением Microsoft Windows 7 или более поздней версии. Для получения наилучших результатов разработки мы рекомендуем Windows 10. Убедитесь, что последние обновления применяются к системе перед установкой Visual Studio.

- Недостаточно свободного дискового пространства. Visual Studio требуется по крайней мере 7 ГБ дискового пространства и может занять не менее 50 ГБ, если установлены много общих параметров. Мы рекомендуем установить его на диске c:.

Сведения о дисковом пространстве и требования к операционной системе см. в разделе [требования к системе для Visual Studio 2017 г](https://www.visualstudio.com/productinfo/vs2017-system-requirements-vs). Программа установки сообщает, требуется место на диске для выбранных параметров.

## <a name="installation"></a>Установка

1. Загрузите последнюю Visual Studio 2017 г. установщик Windows.

   > [!div class="nextstepaction"]
   > <a target="frameTarget" href="https://www.visualstudio.com/thank-you-downloading-visual-studio/?sku=Community&rel=15&utm_source=docs&utm_medium=clickbutton">Установить Visual Studio Community 2017 г.</a>

   >[!Tip]
   > Community edition — для отдельных разработчиков, аудитории обучения, научных исследований и разработки с открытым исходным кодом. Для других целей, установите <a target="frameTarget" href="https://www.visualstudio.com/thank-you-downloading-visual-studio/?sku=Professional&rel=15&utm_source=docs&utm_medium=clickbutton">Visual Studio Professional 2017 г.</a> или <a target="frameTarget" href="https://www.visualstudio.com/thank-you-downloading-visual-studio/?sku=Enterprise&rel=15&utm_source=docs&utm_medium=clickbutton">Visual Studio Enterprise 2017 г</a>.

1. Найдите файл установщика загружаются и запустите его. Могут отображаться в браузере или может оказаться в папке загрузок. Установщик должен иметь права администратора для выполнения. Вы можете увидеть **контроль учетных записей пользователей** диалоговое окно, запрашивающее разрешение дать установщику внести изменения в систему, выбрать **Да**. Если возникают трудности, найдите загруженный файл в проводнике щелкните правой кнопкой мыши значок установщика и выберите **Запуск от имени администратора** в контекстном меню.

   ![Запустите программу установки Visual Studio 2017 г](../build/media/vscpp-concierge-run-installer.gif "запустите установщик Visual Studio")

1. Программа установки предоставляет список рабочих нагрузок, которые представляют собой группы связанные параметры для области разработки. Поддержка C++ теперь является частью необязательно рабочих нагрузок, которые не установлены по умолчанию.

   ![Для разработки настольных приложений с помощью C++](../build/media/desktop-development-with-cpp.png "разработки настольных приложений на C++")

    C++, выберите **разработки настольных приложений с помощью C++** рабочей нагрузки и выберите **установить**.

   ![Установка разработки настольных приложений с помощью рабочей нагрузки C++](../build/media/vscpp-concierge-choose-workload.gif "Установка разработки настольных приложений с помощью C++ рабочей нагрузки")

1. По завершении установки выберите **запуска** кнопку, чтобы запустить Visual Studio.

   Первый раз, при запуске Visual Studio будет предложено войти с учетной записью Майкрософт. Если у вас нет, можно создать один бесплатно. Также необходимо выбрать тему. Не беспокойтесь, его можно изменить позже, если требуется. 

   Может потребоваться Visual Studio несколько минут для начала готов к использованию в первый раз запустить его. Вот, как оно выглядит в небольшой промежуток времени.

   ![Visual Studio 2017 г. Войдите в](../build/media/vscpp-quickstart-first-run.gif "входа Visual Studio 2017 г.")

   Visual Studio запускает гораздо быстрее при его запуске.

1. При запуске среды Visual Studio, проверьте, если значок флажка в заголовке окна будет выделен.

   ![Флаг уведомления Visual Studio 2017 г](../build/media/vscpp-first-start-page-flag.png "флаг уведомления Visual Studio 2017 г.")

   Если он выделен, установите его, чтобы открыть **уведомления** окна. Если имеются доступные обновления для Visual Studio, мы рекомендуем вам установить сейчас. После завершения установки перезапустите Visual Studio.

При запуске Visual Studio, вы готовы продолжить к следующему шагу.

## <a name="next-steps"></a>Дальнейшие действия

> [!div class="nextstepaction"]
> [Шаг 1: Создание проекта C++](vscpp-step-1-create.md)

<iframe src="" height="0" width="0" frameborder="0" name="frameTarget" />
