---
title: 'Элементы ActiveX в MFC: Распространение элементов управления ActiveX | Документация Майкрософт'
ms.custom: ''
ms.date: 09/12/2018
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- GetWindowsDirectory
- GetSystemDirectory
dev_langs:
- C++
helpviewer_keywords:
- MFC ActiveX controls [MFC], ANSI or Unicode versions
- RegSvr32.exe
- MFC ActiveX controls [MFC], distributing
- distributing MFC ActiveX controls
- redistributable files, MFC ActiveX controls
- GetSystemDirectory method [MFC]
- registering ActiveX controls
- MSVCRT40.dll
- registry [MFC], registering controls
- LoadLibrary method, registering ActiveX controls
- MFC40U.DLL
- MFC40.DLL
- GetWindowsDirectory method [MFC]
- installing ActiveX controls
- GetProcAddress method, registering ActiveX controls
- MFC ActiveX controls [MFC], installing
- MFC ActiveX controls [MFC], registering
- registering controls
- OLEPRO32.DLL
ms.assetid: cd70ac9b-f613-4879-9e81-6381fdfda2a1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d75f84a8cb5ca2cb5a867cc640410c7de978d4fc
ms.sourcegitcommit: a3c9e7888b8f437a170327c4c175733ad9eb0454
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2018
ms.locfileid: "50204669"
---
# <a name="mfc-activex-controls-distributing-activex-controls"></a>Элементы управления ActiveX в MFC. Распространение элементов управления ActiveX

В этой статье рассматриваются некоторые проблемы, связанные с распространение элементов управления ActiveX.

- [ANSI или Юникода управления версиями](#_core_ansi_or_unicode_control_versions)

- [Установка элементов управления ActiveX и распространяемых библиотек DLL](#_core_installing_activex_controls_and_redistributable_dlls)

- [Регистрация элементов управления](#_core_registering_controls)

>[!IMPORTANT]
> ActiveX — это устаревшая технология, которая не следует использовать для разработки новых приложений. Дополнительные сведения о современных технологий, заменяющие ActiveX, см. в разделе [элементы управления ActiveX](activex-controls.md).

##  <a name="_core_ansi_or_unicode_control_versions"></a> ANSI или Юникода управления версиями

Необходимо решить, следует ли поставлять ANSI или Юникод версию элемента управления и / или. Это решение основывается на переносимость факторов, присущих наборов символов ANSI и Юникод.

Элементы управления ANSI, которые работают во всех операционных системах Win32, позволяют обеспечить максимальный уровень мобильности между различные операционные системы Win32. Элементы управления Юникода работают в только Windows NT (версии 3.51 или более поздней версии), но не в Windows 95 или Windows 98. Если требуется обеспечение переносимости основной задачей, элементы управления ship ANSI. Если элементы управления будет запускаться только на Windows NT, можно отправлять элементы управления Юникода. Можно также выбрать оба поставляются и установить версию, наилучшим образом подходящий для операционной системы пользователя приложения.

##  <a name="_core_installing_activex_controls_and_redistributable_dlls"></a> Установка элементов управления ActiveX и распространяемых библиотек DLL

Программу установки с элементов управления ActiveX необходимо создать специальные подкаталог каталога Windows и устанавливать элементы управления. В нем файлов OCX.

> [!NOTE]
>  Используйте Windows `GetWindowsDirectory` API в программе установки, чтобы получить имя каталога Windows. Вы можете получить имя вложенного каталога от имени вашу компанию или продукт.

Программе установки необходимо установить необходимые распространяемые файлы DLL в системном каталоге Windows. Если библиотек DLL, они уже присутствуют на компьютере пользователя, программу установки следует сравнить их версий с версиями, выбранный для установки. Переустановка файла только в том случае, если номер его версии больше, чем файл уже установлен.

Так как элементы управления ActiveX может использоваться только в приложениях контейнера OLE, нет необходимости распределять полный набор библиотек DLL OLE с элементами управления. Можно предположить, что приложения-контейнера (или самой операционной системы) имеет стандартный OLE библиотеки DLL.

##  <a name="_core_registering_controls"></a> Регистрация элементов управления

Прежде чем можно будет использовать элемент управления, соответствующие записи должны создаваться для него в базе данных регистрации Windows. Некоторые контейнеры элементов управления ActiveX предоставляют пункта меню для пользователей для регистрации новых элементов управления, но эта функция не могут быть доступны во всех контейнерах. Таким образом вы можете зарегистрировать элементы управления, при установке программа установки.

При желании можно написать программу установки, чтобы зарегистрировать элемент управления напрямую вместо этого.

Используйте `LoadLibrary` Windows API для загрузки библиотеки DLL. Затем используйте `GetProcAddress` получить адрес функции «DllRegisterServer». Наконец, вызовите `DllRegisterServer` функции. В следующем образце кода показано одно из возможных способов, где `hLib` сохраняет дескриптор библиотеки элементов управления, и `lpDllEntryPoint` хранит адрес функции «DllRegisterServer».

[!code-cpp[NVC_MFC_AxCont#16](../mfc/codesnippet/cpp/mfc-activex-controls-distributing-activex-controls_1.cpp)]

Непосредственно регистрации элемента управления удобен тем, что не нужно вызывать и загрузить отдельный процесс (а именно, REGSVR32), сокращение времени установки. Кроме того поскольку внутренний процесс регистрации, программа установки может обрабатывать ошибки и непредвиденных ситуациях лучше, чем внешний процесс может.

> [!NOTE]
>  Прежде чем программа установки установит элемент управления ActiveX, он должен вызывать `OleInitialize`. После завершения программы установки вызовите `OleUnitialize`. Это гарантирует, что OLE системные библиотеки DLL находятся в правильном состоянии для регистрации элемента ActiveX.

Необходимо зарегистрировать MFCx0.DLL.

## <a name="see-also"></a>См. также

[Элементы ActiveX библиотеки MFC](../mfc/mfc-activex-controls.md)

