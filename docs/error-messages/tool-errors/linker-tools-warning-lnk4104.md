---
title: Предупреждение средств компоновщика LNK4104 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4104
dev_langs:
- C++
helpviewer_keywords:
- LNK4104
ms.assetid: ca6728db-d616-419a-a570-65e8445c6079
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6304f3ea928c89f4756a4594270ebb7914324f85
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46057266"
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