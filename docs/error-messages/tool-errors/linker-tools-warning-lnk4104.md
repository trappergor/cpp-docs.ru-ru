---
title: Предупреждение средств компоновщика LNK4104
ms.date: 11/04/2016
f1_keywords:
- LNK4104
helpviewer_keywords:
- LNK4104
ms.assetid: ca6728db-d616-419a-a570-65e8445c6079
ms.openlocfilehash: 3d89b27c32b33b917abb7fc140eebf5924142423
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50668130"
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