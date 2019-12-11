---
title: Предупреждение средств компоновщика LNK4247
ms.date: 11/04/2016
f1_keywords:
- LNK4247
helpviewer_keywords:
- LNK4247
ms.assetid: 085d7fdf-9eaf-4641-8473-6eaadd073c7b
ms.openlocfilehash: 344c219fa1f3daa1e5f9c31431e608f5e7036400
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2019
ms.locfileid: "74991154"
---
# <a name="linker-tools-warning-lnk4247"></a>Предупреждение средств компоновщика LNK4247

точка входа "decorated_function_name" уже имеет атрибут потока; атрибут "Attribute" проигнорирован

Также указана точка входа, указанная с параметром [/Entry (символ точки входа)](../../build/reference/entry-entry-point-symbol.md), но [/CLRTHREADATTRIBUTE (Установка атрибута потока CLR)](../../build/reference/clrthreadattribute-set-clr-thread-attribute.md) и с другой потоковой моделью.

Компоновщик проигнорировал значение, указанное с помощью/КЛРСРЕАДАТТРИБУТЕ.

Чтобы устранить это предупреждение, сделайте следующее:

- Удалите/CLRTHREADATTRIBUTE из сборки.

- Удалите атрибут из файла исходного кода.

- Удалите атрибут из Source и/CLRTHREADATTRIBUTE из сборки и примите модель потоков CLR по умолчанию.

- Измените значение, передаваемое в/CLRTHREADATTRIBUTE, таким, что оно соглашается с атрибутом в источнике.

- Измените атрибут в источнике, так что он соглашается со значением, переданным в/КЛРСРЕАДАТТРИБУТЕ.

Следующий пример приводит к возникновению ошибки LNK4247

```cpp
// LNK4247.cpp
// compile with: /clr /c
// post-build command: link /CLRTHREADATTRIBUTE:STA LNK4247.obj /entry:functionTitle /SUBSYSTEM:Console
[System::MTAThreadAttribute]
void functionTitle (){}
```
