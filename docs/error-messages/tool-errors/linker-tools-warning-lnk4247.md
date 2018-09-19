---
title: Предупреждение средств компоновщика LNK4247 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4247
dev_langs:
- C++
helpviewer_keywords:
- LNK4247
ms.assetid: 085d7fdf-9eaf-4641-8473-6eaadd073c7b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2d84a5964cb8df5d2973b6031da55d48dade584e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46078014"
---
# <a name="linker-tools-warning-lnk4247"></a>Предупреждение средств компоновщика LNK4247

точка входа «декорированное_имя_функции» уже есть атрибут потока; «атрибут» игнорируется

Точки входа, указанный с помощью [/Entry (символ точки входа)](../../build/reference/entry-entry-point-symbol.md), имели атрибут потока, но [/CLRTHREADATTRIBUTE (значение атрибута потока среды CLR)](../../build/reference/clrthreadattribute-set-clr-thread-attribute.md) также указано, с другой моделью потоков.

Компоновщик игнорирует значение, указанное с помощью /CLRTHREADATTRIBUTE.

Чтобы устранить это предупреждение:

- Удалите /CLRTHREADATTRIBUTE из сборки.

- Удалите атрибут из файла исходного кода.

- Удалите атрибут из источника и параметр/CLRTHREADATTRIBUTE из сборки и примите потоковой моделью среды CLR по умолчанию.

- Измените значение, передаваемое /CLRTHREADATTRIBUTE, таким образом, что оно согласуется с атрибутом в источнике.

- Измените атрибут в источнике, таким образом, что оно согласуется со значением, передаваемым в /CLRTHREADATTRIBUTE.

Следующий пример приводит к возникновению ошибки LNK4247

```
// LNK4247.cpp
// compile with: /clr /c
// post-build command: link /CLRTHREADATTRIBUTE:STA LNK4247.obj /entry:functionTitle /SUBSYSTEM:Console
[System::MTAThreadAttribute]
void functionTitle (){}
```