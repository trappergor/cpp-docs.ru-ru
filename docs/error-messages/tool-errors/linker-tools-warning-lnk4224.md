---
title: Предупреждение средств компоновщика LNK4224
ms.date: 11/04/2016
f1_keywords:
- LNK4224
helpviewer_keywords:
- LNK4224
ms.assetid: 8624b70e-0b93-43cf-b457-834d38632d0b
ms.openlocfilehash: eb0a019cc80e5218a52697b8bcd5e91b811d04d3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62160397"
---
# <a name="linker-tools-warning-lnk4224"></a>Предупреждение средств компоновщика LNK4224

> *параметр* больше не поддерживается; пропускается

## <a name="remarks"></a>Примечания

Указан недопустимый устаревший параметр компоновщика и проигнорировано.

Например, LNK4224 может возникать, если директива/Comment отображается в. obj. Директива/Comment добавляемого через [комментарий (C/C++)](../../preprocessor/comment-c-cpp.md) pragma, с помощью параметром exestr. Использование служебной программы dumpbin [/ALL](../../build/reference/all.md) для просмотра директивы компоновщика в OBJ-файле.

Если это возможно измените источник для OBJ-файл и удалите директиву pragma. Если пропустить это предупреждение, не исключено, что ошибок скомпилирован с **/CLR: pure** будет работать неправильно. **/CLR: pure** параметр компилятора в Visual Studio 2015 не рекомендуется и не поддерживается в Visual Studio 2017.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки LNK4224.

```cpp
// LNK4224.cpp
// compile with: /c /Zi
// post-build command: link LNK4224.obj /debug /debugtype:map
int main () {
   return 0;
}
```