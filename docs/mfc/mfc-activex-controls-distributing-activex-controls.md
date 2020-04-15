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
ms.openlocfilehash: 1ada1c801b2d9d62f1cc4cd5bf72a2995225b3de
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364628"
---
# <a name="mfc-activex-controls-distributing-activex-controls"></a>Элементы управления ActiveX в MFC. Распространение элементов управления ActiveX

В этой статье рассматриваются несколько вопросов, связанных с перераспределением элементов управления ActiveX:

- [Версии управления ANSI или Unicode](#_core_ansi_or_unicode_control_versions)

- [Установка ActiveX Управления и Redistributable DLLs](#_core_installing_activex_controls_and_redistributable_dlls)

- [Контроль регистрации](#_core_registering_controls)

>[!IMPORTANT]
> ActiveX является устаревшей технологией, которая не должна использоваться для новых разработок. Для получения дополнительной информации о современных технологиях, которые заменяли ActiveX, [см.](activex-controls.md)

## <a name="ansi-or-unicode-control-versions"></a><a name="_core_ansi_or_unicode_control_versions"></a>Версии управления ANSI или Unicode

Вы должны решить, следует ли отправить ANSI или Unicode версию управления, или оба. Это решение основано на факторах переносимости, присущих наборам символов ANSI и Unicode.

Элементы управления ANSI, которые работают на всех операционных системах Win32, обеспечивают максимальную портативность между различными операционными системами Win32. Элементы управления Unicode работают только на Windows NT (версия 3.51 или более поздней версии), но не на Windows 95 или Windows 98. Если портативность является вашей главной заботой, корабль ANSI управления. Если элементы управления будут работать только на Windows NT, вы можете отправить элементы управления Unicode. Вы также можете отправить оба и установить приложение наиболее подходящей для операционной системы пользователя.

## <a name="installing-activex-controls-and-redistributable-dlls"></a><a name="_core_installing_activex_controls_and_redistributable_dlls"></a>Установка ActiveX Управления и Redistributable DLLs

Программа настройки, предоставляемая с помощью элементов управления ActiveX, должна создать специальную субдиректорьную часть каталога Windows и установить элементы управления». Файлы OCX в нем.

> [!NOTE]
> Используйте `GetWindowsDirectory` API Windows в программе настройки для получения названия каталога Windows. Вы можете получить название субдиректоров от названия вашей компании или продукта.

Программа настройки должна установить необходимые перераспределителистные dLL-файлы в каталог системы Windows. Если какой-либо из DLLs уже присутствует на машине пользователя, программа настройки должна сравнить их версии с версиями, которые вы устанавливаете. Переустановите файл только в том случае, если его номер версии выше, чем уже установленный файл.

Поскольку элементы управления ActiveX могут использоваться только в контейнерных приложениях OLE, нет необходимости распространять полный набор OL DLLs с вашими элементами управления. Можно предположить, что в содержащем приложении (или самой операционной системе) установлены стандартные OLE DLL.

## <a name="registering-controls"></a><a name="_core_registering_controls"></a>Контроль регистрации

Перед тем, как можно использовать элемент управления, для него должны быть созданы соответствующие записи в базе данных регистрации Windows. Некоторые контейнеры управления ActiveX предоставляют пользователям элемент меню для регистрации новых элементов управления, но эта функция может быть доступна не во всех контейнерах. Поэтому может потребоваться регистрация программы настройки при установке элементов управления.

Если вы предпочитаете, вы можете написать программу настройки, чтобы зарегистрировать элемент управления непосредственно вместо этого.

Используйте `LoadLibrary` API Windows для загрузки управления DLL. Затем используйте `GetProcAddress` для получения адреса функции "DllRegisterServer". Наконец, `DllRegisterServer` вызов функции. Следующий пример кода демонстрирует один `hLib` возможный метод, при котором `lpDllEntryPoint` хранится ручка библиотеки управления и сохраняет адрес функции "DllRegisterServer".

[!code-cpp[NVC_MFC_AxCont#16](../mfc/codesnippet/cpp/mfc-activex-controls-distributing-activex-controls_1.cpp)]

Преимущество непосредственной регистрации элемента управления заключается в том, что вам не нужно вызывать и загружать отдельный процесс (а именно, REGSVR32), сокращая время установки. Кроме того, поскольку регистрация является внутренним процессом, программа настройки может обрабатывать ошибки и непредвиденные ситуации лучше, чем внешний процесс.

> [!NOTE]
> Перед тем, как программа настройки установит элемент `OleInitialize`управления ActiveX, он должен вызвать. Когда программа настройки будет `OleUnitialize`закончена, позвоните. Это гарантирует, что система OL DLL находятся в надлежащем состоянии для регистрации управления ActiveX.

Вы должны зарегистрировать MFCx0.DLL.

## <a name="see-also"></a>См. также раздел

[Элементы ActiveX библиотеки MFC](../mfc/mfc-activex-controls.md)
