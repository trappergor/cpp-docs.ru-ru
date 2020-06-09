---
title: Элементы управления ActiveX в MFC. Распространение элементов управления ActiveX
ms.date: 09/12/2018
f1_keywords:
- GetWindowsDirectory
- GetSystemDirectory
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
ms.openlocfilehash: 11d647922a4f8097e03e112c0c93c833524c2c4e
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84618208"
---
# <a name="mfc-activex-controls-distributing-activex-controls"></a>Элементы управления ActiveX в MFC. Распространение элементов управления ActiveX

В этой статье рассматриваются некоторые проблемы, связанные с распространением элементов управления ActiveX.

- [Версии элементов управления ANSI или Unicode](#_core_ansi_or_unicode_control_versions)

- [Установка элементов управления ActiveX и распространяемых библиотек DLL](#_core_installing_activex_controls_and_redistributable_dlls)

- [Регистрация элементов управления](#_core_registering_controls)

>[!IMPORTANT]
> ActiveX — это устаревшая технология, которую не следует использовать для новой разработки. Дополнительные сведения о современных технологиях, которые заменяют ActiveX, см. в разделе [элементы управления ActiveX](activex-controls.md).

## <a name="ansi-or-unicode-control-versions"></a><a name="_core_ansi_or_unicode_control_versions"></a>Версии элементов управления ANSI или Unicode

Необходимо решить, следует ли поставлять версию элемента управления в формате ANSI или Unicode или и то, и другое. Это решение основано на коэффициентах переносимости, присущих кодировкам ANSI и Юникод.

Элементы управления ANSI, работающие во всех операционных системах Win32, обеспечивают максимальную переносимость между различными операционными системами Win32. Элементы управления Юникода работают только в Windows NT (версии 3,51 или более поздней), но не в Windows 95 или Windows 98. Если есть основная проблема переносимости, поставьте элементы управления ANSI. Если элементы управления будут работать только в Windows NT, можно поставлять элементы управления Юникод. Вы также можете поставлять и приложение, и установить для него версию, наиболее подходящую для операционной системы пользователя.

## <a name="installing-activex-controls-and-redistributable-dlls"></a><a name="_core_installing_activex_controls_and_redistributable_dlls"></a>Установка элементов управления ActiveX и распространяемых библиотек DLL

Программа установки, предоставляемая элементами управления ActiveX, должна создать специальный подкаталог каталога Windows и установить элементы управления. Файлы OCX в нем.

> [!NOTE]
> Используйте API Windows `GetWindowsDirectory` в программе установки, чтобы получить имя каталога Windows. Может потребоваться получить имя подкаталога от имени вашей компании или продукта.

Программа установки должна установить необходимые распространяемые DLL-файлы в системный каталог Windows. Если какая-либо из библиотек DLL уже существует на компьютере пользователя, программа установки должна сравнить свои версии с устанавливаемыми версиями. Переустановите файл, только если его номер версии выше, чем уже установленный файл.

Поскольку элементы управления ActiveX могут использоваться только в приложениях-контейнерах OLE, нет необходимости распространять полный набор библиотек DLL OLE с элементами управления. Можно предположить, что в содержащем его приложении (или в самой операционной системе) установлены стандартные DLL-библиотеки OLE.

## <a name="registering-controls"></a><a name="_core_registering_controls"></a>Регистрация элементов управления

Прежде чем можно будет использовать элемент управления, для него должны быть созданы соответствующие записи в базе данных регистрации Windows. Некоторые контейнеры элементов управления ActiveX предоставляют пользователю пункт меню для регистрации новых элементов управления, но эта функция может быть недоступна во всех контейнерах. Таким образом, программе установки может потребоваться зарегистрировать элементы управления при их установке.

При желании вы можете написать программу установки для непосредственной регистрации элемента управления.

Используйте `LoadLibrary` API Windows для загрузки библиотеки DLL элемента управления. Затем используйте `GetProcAddress` для получения адреса функции DllRegisterServer. Наконец, вызовите `DllRegisterServer` функцию. В следующем примере кода показан один из возможных методов, где `hLib` хранит маркер библиотеки элементов управления и `lpDllEntryPoint` сохраняет адрес функции DllRegisterServer.

[!code-cpp[NVC_MFC_AxCont#16](codesnippet/cpp/mfc-activex-controls-distributing-activex-controls_1.cpp)]

Преимуществом регистрации элемента управления напрямую является отсутствие необходимости вызывать и загружать отдельный процесс (а именно, REGSVR32), уменьшая время установки. Кроме того, поскольку регистрация является внутренним процессом, программа установки может обрабатывать ошибки и непредвиденные ситуации лучше, чем внешний процесс.

> [!NOTE]
> Перед установкой элемента управления ActiveX программа установки должна вызвать `OleInitialize` . После завершения программы установки вызовите `OleUnitialize` . Это гарантирует, что системные DLL-библиотеки OLE находятся в правильном состоянии для регистрации элемента управления ActiveX.

Необходимо зарегистрировать MFCx0. DLL.

## <a name="see-also"></a>См. также раздел

[Элементы ActiveX библиотеки MFC](mfc-activex-controls.md)
