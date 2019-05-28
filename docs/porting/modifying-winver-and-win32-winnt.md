---
title: Изменение WINVER и _WIN32_WINNT
ms.date: 09/04/2017
helpviewer_keywords:
- WINVER in an upgraded Visual Studio C++ project
- _WIN32_WINNT in an upgraded Visual Studio C++ project
ms.assetid: 6a1f1d66-ae0e-48a7-81c3-524d8e8f3447
ms.openlocfilehash: a624118bdd192c5ec677be81f0b410d2392e62e9
ms.sourcegitcommit: 7d64c5f226f925642a25e07498567df8bebb00d4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2019
ms.locfileid: "65449070"
---
# <a name="modifying-winver-and-win32winnt"></a>Изменение WINVER и _WIN32_WINNT

Visual C++ больше не поддерживает создание программ для Windows 95, Windows 98, Windows ME, Windows NT и Windows 2000. Если ваши макросы **WINVER** или **_WIN32_WINNT** предназначены для одной из этих версий Windows, необходимо изменить такие макросы. При обновлении проекта, созданного с помощью более ранней версии Visual C++, могут появиться ошибки компиляции, связанные с макросами **WINVER** или **_WIN32_WINNT** , если они назначены версии Windows, которая больше не поддерживается.

## <a name="remarks"></a>Примечания

Чтобы изменить макросы, в файле заголовка (например, targetver.h, который включается при создании проекта для Windows) добавьте следующие строки.

```C
#define WINVER 0x0A00
#define _WIN32_WINNT 0x0A00
```

В данном случае целевой операционной системой является Windows 10. Эти значения перечислены в файле заголовка Windows SDKDDKVer.h, который также определяет макросы для каждой версии Windows. Перед включением файла SDKDDKVer.h необходимо добавить выражение #define. Далее приводятся строки из версии SDKDDKVer.h для Windows 10, которые кодируют значения для каждой версии Windows.

```C
//
// _WIN32_WINNT version constants
//
#define _WIN32_WINNT_NT4                    0x0400 // Windows NT 4.0
#define _WIN32_WINNT_WIN2K                  0x0500 // Windows 2000
#define _WIN32_WINNT_WINXP                  0x0501 // Windows XP
#define _WIN32_WINNT_WS03                   0x0502 // Windows Server 2003
#define _WIN32_WINNT_WIN6                   0x0600 // Windows Vista
#define _WIN32_WINNT_VISTA                  0x0600 // Windows Vista
#define _WIN32_WINNT_WS08                   0x0600 // Windows Server 2008
#define _WIN32_WINNT_LONGHORN               0x0600 // Windows Vista
#define _WIN32_WINNT_WIN7                   0x0601 // Windows 7
#define _WIN32_WINNT_WIN8                   0x0602 // Windows 8
#define _WIN32_WINNT_WINBLUE                0x0603 // Windows 8.1
#define _WIN32_WINNT_WINTHRESHOLD           0x0A00 // Windows 10
#define _WIN32_WINNT_WIN10                  0x0A00 // Windows 10
```

Если эти версии Windows отсутствуют в просматриваемой копии SDKDDKVer.h, возможно, вы используете старую версию пакета SDK Windows. По умолчанию для проектов Win32 в Visual Studio 2017 используется пакет SDK Windows 10.

> [!NOTE]
> Значения могут не сработать, если включить в приложение внутренние заголовки MFC.

Также можно определить этот макрос с помощью параметра компилятора `/D`. Для получения дополнительной информации см. [/D (Preprocessor Definitions)](../build/reference/d-preprocessor-definitions.md).

Дополнительные сведения о значении этих макросов см. в разделе [Использование заголовков Windows](/windows/desktop/WinProg/using-the-windows-headers).

## <a name="see-also"></a>См. также

[Журнал изменений Visual C++](../porting/visual-cpp-change-history-2003-2015.md)
