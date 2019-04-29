---
title: Предупреждение средств компоновщика LNK4104
ms.date: 11/04/2016
f1_keywords:
- LNK4104
helpviewer_keywords:
- LNK4104
ms.assetid: ca6728db-d616-419a-a570-65e8445c6079
ms.openlocfilehash: 3d89b27c32b33b917abb7fc140eebf5924142423
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62298546"
---
# <a name="linker-tools-warning-lnk4104"></a>Предупреждение средств компоновщика LNK4104

Экспорт символа «символ» должен быть PRIVATE

`symbol` Может принимать одно из следующих:

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

Это предупреждение создается, когда вы создаете библиотеку импорта для библиотеки DLL и экспортировать одну из перечисленных выше функций без указания ее как PRIVATE в файл определения модуля. Как правило эти функции экспортируются для использования только с OLE. Их размещения в библиотеке импорта можно привести к непредвиденному поведению, когда программа связана с библиотекой неправильно выполняет вызовы к ним. Дополнительные сведения о PRIVATE-ключевое слово, см. в разделе [ЭКСПОРТОВ](../../build/reference/exports.md).