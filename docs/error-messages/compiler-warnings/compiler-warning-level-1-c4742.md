---
title: Предупреждение компилятора (уровень 1) C4742
ms.date: 11/04/2016
f1_keywords:
- C4742
helpviewer_keywords:
- C4742
ms.assetid: e520881d-1eeb-48b1-9df0-8017ee8ba076
ms.openlocfilehash: 11663a9b8672e2f91feb59e275181dbe645484e9
ms.sourcegitcommit: 458dcc794e3841919c01a3a5ff6b9a3767f8861b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/13/2019
ms.locfileid: "74051311"
---
# <a name="compiler-warning-level-1-c4742"></a>Предупреждение компилятора (уровень 1) C4742

"var" имеет разное выравнивание в "file1" и "File2": число и число

Внешняя переменная, на которую ссылается или определена в двух файлах, имеет различное выравнивание в этих файлах. Это предупреждение выдается при обнаружении компилятором того, что `__alignof` для переменной в *file1* отличается от `__alignof` для переменной в *file2*. Это может быть вызвано использованием несовместимых типов при объявлении переменной в разных файлах или при использовании несовпадающих `#pragma pack` в разных файлах.

Чтобы устранить это предупреждение, используйте одно и то же определение типа или используйте разные имена для переменных.

Дополнительные сведения см. в разделе Оператор [Pack](../../preprocessor/pack.md) и [__alignof](../../cpp/alignof-operator.md).

## <a name="example"></a>Пример

Это первый файл, определяющий тип.

```c
// C4742a.c
// compile with: /c
struct X {
   char x, y, z, w;
} global;
```

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C4742.

```c
// C4742b.c
// compile with: C4742a.c /W1 /GL
// C4742 expected
extern struct X {
   int a;
} global;

int main() {
   global.a = 0;
}
```