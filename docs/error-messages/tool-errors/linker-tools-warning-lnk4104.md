---
title: Предупреждение средств компоновщика LNK4104
ms.date: 11/04/2016
f1_keywords:
- LNK4104
helpviewer_keywords:
- LNK4104
ms.assetid: ca6728db-d616-419a-a570-65e8445c6079
ms.openlocfilehash: 604dccf01b3dffc0060546bebf19d64c16ebf965
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80193970"
---
# <a name="linker-tools-warning-lnk4104"></a>Предупреждение средств компоновщика LNK4104

Экспорт символа "символ" должен быть частным

`symbol` может быть одним из следующих:

- `DllCanUnloadNow`

- `DllGetClassObject`

- `DllGetClassFactoryFromClassString`

- `DllGetDocumentation`

- `DllInitialize`

- `DllInstall`

- `DllRegisterServer`

- `DllRegisterServerEx`

- `DllRegisterServerExW`

- `DllUnload`

- `DllUnregisterServer`

- `RasCustomDeleteEntryNotify`

- `RasCustomDial`

- `RasCustomDialDlg`

- `RasCustomEntryDlg`

Это предупреждение выдается при построении библиотеки импорта для библиотеки DLL и экспорта одной из указанных выше функций без указания ее в качестве ЗАКРЫТой в файле определения модуля. Как правило, эти функции экспортируются для использования только OLE. Помещение их в библиотеку импорта может привести к необычному поведению, когда программа, связанная с библиотекой, неправильно выполняет вызовы. Дополнительные сведения о ключевом слове PRIVATE см. в разделе [EXPORTS](../../build/reference/exports.md).
