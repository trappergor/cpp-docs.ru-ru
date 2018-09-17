---
title: Установка поддержки C++ в Visual Studio 2017 | Документация Майкрософт
description: Поддержка Visual C++ в Visual Studio
ms.custom: mvc
ms.date: 06/21/2018
ms.topic: tutorial
ms.technology:
- devlang-C++
ms.devlang: C++
dev_langs:
- C++
ms.assetid: 45138d70-719d-42dc-90d7-1d0ca31a2f54
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b3e0fef319fbe119118e3a915a66bea3546bbb9a
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45702901"
---
# <a name="install-c-support-in-visual-studio"></a>Установка поддержки C++ в Visual Studio

Если вы еще не скачали и установлен на компьютере Visual Studio 2017 и инструменты Visual C++, вот как приступить к работе.

## <a name="prerequisites"></a>Предварительные требования

- Высокоскоростное подключение к Интернету. В установщике Visual Studio можно загрузить несколько гигабайт данных.

- Компьютер под управлением Microsoft Windows 7 или более поздних версий. Мы рекомендуем использовать Windows 10 для обеспечения оптимальной среды разработки. Убедитесь, что последние обновления применяются к системе перед установкой Visual Studio.

- Недостаточно свободного места на диске. Visual Studio требуется по крайней мере 7 ГБ пространства на диске и может занять не менее 50 ГБ, если устанавливаются многие общие параметры. Мы рекомендуем установить на диске C:.

Дополнительные сведения о дисковом пространстве и требования к операционной системе, см. в разделе [Visual Studio семейства требования к системе продуктов](/visualstudio/productinfo/vs2017-system-requirements-vs). Установщик сообщает, сколько места на диске необходим для выбранных параметров.

## <a name="visual-studio-2015-installation"></a>Visual Studio 2015 установки

Установить Visual Studio 2015 можно из раздела [Скачивание более старых версий Visual Studio](https://www.visualstudio.com/vs/older-downloads/). Запустите программу установки и щелкните **Выборочная установка**, а затем выберите компонент C++.

Как правило, рекомендуется использовать Visual Studio 2017, даже если вам нужно скомпилировать код в компиляторе Visual Studio 2015. Дополнительные сведения см. в разделе [Использование собственного многоплатформенного нацеливания в Visual Studio для сборки старых проектов](../porting/use-native-multi-targeting.md).

## <a name="visual-studio-2017-installation"></a>Visual Studio 2017 установки

1. Скачайте последнюю версию установщика Visual Studio 2017 для Windows.

   > [!div class="nextstepaction"]
   > [Установить Visual Studio 2017 Community](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017)

   >[!Tip]
   > Выпуск Community предназначен для индивидуальных разработчиков, использования при аудиторном обучении и в научных исследованиях, а также разработки решений с открытым кодом. В других целях установите [Visual Studio 2017 Professional](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) или [Visual Studio 2017 Enterprise](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017).

1. Найдите файл установщика, вы скачали и запустите его. Она может отображаться в браузере, или может оказаться в папке загрузок. Программа установки требуются права администратора для выполнения. Может появиться **контроль учетных записей пользователей** диалоговое окно с предложением предоставить разрешение на дать установщику внести изменения в систему; выберите **Да**. Если у вас возникают проблемы, найдите скачанный файл в проводнике щелкните правой кнопкой мыши значок установщика и выберите **Запуск от имени администратора** в контекстном меню.

   ![Запустите установщик Visual Studio 2017](../build/media/vscpp-concierge-run-installer.gif "запустите установщик Visual Studio")

1. В установщике предлагается список рабочих нагрузок, то есть групп связанных параметров для определенных целей разработки. Поддержка C++ теперь является частью необязательно рабочих нагрузок, которые не устанавливаются по умолчанию.

   ![Разработка классических приложений C++](../build/media/desktop-development-with-cpp.png "разработка классических приложений C++")

   C++, выберите **разработка классических приложений C++** рабочей нагрузки и выберите **установить**.

   ![Установка Разработка настольных приложений с помощью рабочей нагрузки C++](../build/media/vscpp-concierge-choose-workload.gif "Установка Разработка настольных приложений с помощью рабочей нагрузки C++")

1. По завершении установки выберите **запуска** кнопку, чтобы запустить Visual Studio.

   При первом запуске Visual Studio будет предложено выполнить вход с использованием учетной записи Майкрософт. Если у вас ее нет, его можно создать бесплатно. Также необходимо выбрать тему. Не беспокойтесь, можно изменить его позже, если вы хотите.

   Может потребоваться Visual Studio несколько минут для подготовки к использования в первый раз, запустите его. Вот, как оно выглядит в небольшой промежуток времени.

   ![Вход Visual Studio 2017](../build/media/vscpp-quickstart-first-run.gif "вход Visual Studio 2017")

   Visual Studio запускает намного быстрее при повторном запуске.

1. При запуске среды Visual Studio, проверьте, если значок флажка в заголовке окна будет выделен.

   ![Флаг уведомления Visual Studio 2017](../build/media/vscpp-first-start-page-flag.png "флаг уведомления Visual Studio 2017")

   Если он будет выделен, выберите его, чтобы открыть **уведомления** окна. Если доступны все обновления для Visual Studio, мы рекомендуем установить их сейчас. После завершения установки перезапустите Visual Studio.

Когда выполняется Visual Studio, можно приступать к выполнению следующего шага.

## <a name="next-steps"></a>Следующие шаги

> [!div class="nextstepaction"]
> [Создание проекта C++](vscpp-step-1-create.md)

<iframe src="" height="0" width="0" frameborder="0" name="frameTarget" />
