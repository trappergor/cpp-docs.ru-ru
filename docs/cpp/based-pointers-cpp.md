---
title: Основанные указатели (C++)
ms.date: 10/09/2018
f1_keywords:
- __based
- _based
- __based_cpp
helpviewer_keywords:
- __based keyword [C++]
- based pointers
- pointers, based
ms.assetid: 1e5f2e96-c52e-4738-8e14-87278681205e
ms.openlocfilehash: 24c3a7f85c4ea05c38f3ab1d3f637ea0ab24d4c5
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81363747"
---
# <a name="based-pointers-c"></a>Основанные указатели (C++)

Ключевое **__based** позволяет декларировать указатели на основе указателей (указателей, которые являются смещениями от существующих указателей). Ключевое слово **__based** — это специфичное слово Майкрософт.

## <a name="syntax"></a>Синтаксис

```
type __based( base ) declarator
```

## <a name="remarks"></a>Remarks

Указатели, основанные на адресах указателей, являются единственной формой ключевого слова **__based,** действительным в 32-битных или 64-битных компиляциях. В 32-разрядном компиляторе Microsoft C/C++ относительный указатель имеет 32-разрядное смещение от 32-разрядной базы указателя. То же ограничение действует и для 64-разрядных сред, где относительный указатель имеет 64-разрядное смещение от 64-разрядной базы указателя.

Указатели на основе указателей, в частности, используются для постоянных идентификаторов, которые содержат указатели. Связанный список, состоящий из указателей на основе указателей, можно сохранить на диск, а затем перезагрузить в другое место в памяти. При этом все указатели останутся действительными. Пример:

```cpp
// based_pointers1.cpp
// compile with: /c
void *vpBuffer;
struct llist_t {
   void __based( vpBuffer ) *vpData;
   struct llist_t __based( vpBuffer ) *llNext;
};
```

Указателю `vpBuffer` назначается адрес в памяти, который выделяется на более позднем этапе программы. Связанный список перемещается относительно значения `vpBuffer`.

> [!NOTE]
> Сохраняющиеся идентификаторы, содержащие указатели, также могут быть выполнены с помощью [файлов с картографированными памятью.](/windows/win32/Memory/file-mapping)

Когда выполняется разыменовывание относительных указателей, база должна быть либо явно указана, либо неявно известна из объявления.

Для совместимости с предыдущими версиями **_based** является синонимом **для __based** если не указан абонементы компилятора [/ расширения языка с помощью qA \(Disable.](../build/reference/za-ze-disable-language-extensions.md)

## <a name="example"></a>Пример

В следующем примере демонстрируется изменение относительного указателя путем изменения его базы.

```cpp
// based_pointers2.cpp
// compile with: /EHsc
#include <iostream>

int a1[] = { 1,2,3 };
int a2[] = { 10,11,12 };
int *pBased;

typedef int __based(pBased) * pBasedPtr;

using namespace std;
int main() {
   pBased = &a1[0];
   pBasedPtr pb = 0;

   cout << *pb << endl;
   cout << *(pb+1) << endl;

   pBased = &a2[0];

   cout << *pb << endl;
   cout << *(pb+1) << endl;
}
```

```Output
1
2
10
11
```

## <a name="see-also"></a>См. также раздел

[Keywords](../cpp/keywords-cpp.md)<br/>
[alloc_text](../preprocessor/alloc-text.md)
