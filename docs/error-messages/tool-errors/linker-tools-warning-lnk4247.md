---
title: Предупреждение средств компоновщика LNK4247
ms.date: 11/04/2016
f1_keywords:
- LNK4247
helpviewer_keywords:
- LNK4247
ms.assetid: 085d7fdf-9eaf-4641-8473-6eaadd073c7b
ms.openlocfilehash: cd4108f8bd06ec7a0b2d2eb9fab13917174b797b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50516029"
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