---
title: "Элементы управления ActiveX MFC: Распространение элементов управления ActiveX | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e4ce6602696f733ca3bac03441a58515c57e0dc1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="mfc-activex-controls-distributing-activex-controls"></a>Элементы управления ActiveX в MFC. Распространение элементов управления ActiveX
В этой статье рассматриваются некоторые проблемы, связанные с распространение элементов управления ActiveX.  
  
-   [ANSI или Юникода управления версиями](#_core_ansi_or_unicode_control_versions)  
  
-   [Установка элементов управления ActiveX и распространяемых библиотек DLL](#_core_installing_activex_controls_and_redistributable_dlls)  
  
-   [Регистрация элементов управления](#_core_registering_controls)  
  
##  <a name="_core_ansi_or_unicode_control_versions"></a>ANSI или Юникода управления версиями  
 Необходимо решить, будет ли поставлять версию элемента управления или как ANSI или Юникод. Это решение на основе переносимость факторов заложенных в кодировках ANSI и Юникод.  
  
 Элементы управления ANSI, которые работают во всех операционных системах Win32, разрешить для обеспечения максимальной переносимости между различными операционными системами Win32. Элементы управления Юникода работают только с Windows NT (версии 3.51 или более поздней версии), но не в Windows 95 или Windows 98. Если требуется обеспечить переносимость основной задачей, элементы управления ANSI отгрузки. Если элементы управления будет выполняться только в Windows NT, могут поставляться элементы управления Юникода. Можно также выбрать оба поставлен и установите версию, наиболее подходящим для операционной системы пользователя приложения.  
  
##  <a name="_core_installing_activex_controls_and_redistributable_dlls"></a>Установка элементов управления ActiveX и распространяемых библиотек DLL  
 Программу установки с элементов управления ActiveX необходимо создать специальные подкаталог каталога Windows и установите элементы управления. OCX-файлы в ней.  
  
> [!NOTE]
>  Использование окон **GetWindowsDirectory** API в программу установки, чтобы получить имя каталога Windows. Можно наследовать имя подкаталога имя вашу компанию или продукт.  
  
 Программе установки необходимо установить необходимые распространяемые файлы DLL в системном каталоге Windows. Если библиотек DLL, они уже присутствуют на компьютере пользователя, программа установки следует сравнить их версии с версиями, при установке. Переустановка файла только в том случае, если номер версии выше, чем файл уже установлен.  
  
 Поскольку элементы управления ActiveX можно использовать только в OLE-приложения контейнера, нет необходимости распределять полный набор библиотек динамической компоновки OLE с элементами управления. Можно предположить наличие стандартных библиотек динамической компоновки OLE установлены приложение (или самой операционной системы).  
  
##  <a name="_core_registering_controls"></a>Регистрация элементов управления  
 Перед тем как использовать элемент управления, соответствующие записи должны создаваться для его регистрации базы данных Windows. Некоторые контейнеры элементов управления ActiveX предоставляют пункта меню пользователи могут регистрировать новые элементы управления, но этот компонент не доступны во всех контейнерах. Таким образом вы можете зарегистрировать элементы управления при установке программа установки.  
  
 При желании можно написать программу установки, чтобы зарегистрировать элемент управления напрямую вместо.  
  
 Используйте **LoadLibrary** API Windows для загрузки библиотеки DLL элемента управления. Затем используйте **GetProcAddress** получить адрес функции «DllRegisterServer». Наконец, вызовите `DllRegisterServer` функции. В следующем образце кода демонстрируется один из возможных способов, где `hLib` сохранение дескриптора библиотеки элементов управления и `lpDllEntryPoint` хранит адрес функции «DllRegisterServer».  
  
 [!code-cpp[NVC_MFC_AxCont#16](../mfc/codesnippet/cpp/mfc-activex-controls-distributing-activex-controls_1.cpp)]  
  
 Преимуществом непосредственно Регистрация элемента управления является не необходимость вызова неуправляемого кода и загрузить в отдельном процессе (а именно, REGSVR32), что сокращает время установки. Кроме того поскольку регистрации во внутреннем процессе, программа установки может обрабатывать ошибки, и может непредвиденных ситуаций лучше, чем внешний процесс.  
  
> [!NOTE]
>  Прежде чем программа установки устанавливает элемент управления ActiveX, он должен вызывать **OleInitialize**. После завершения программы установки, вызовите **OleUnitialize**. Это обеспечит OLE системные библиотеки DLL в правильном состоянии для регистрации элемента ActiveX.  
  
 Необходимо зарегистрировать MFCx0.DLL.  
  
## <a name="see-also"></a>См. также  
 [Элементы ActiveX библиотеки MFC](../mfc/mfc-activex-controls.md)

