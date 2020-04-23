---
title: Предупреждение компилятора (уровень 1) C4291
ms.date: 11/04/2016
f1_keywords:
- C4291
helpviewer_keywords:
- C4291
ms.assetid: c2b95dea-38f2-4609-9104-707c30798da4
ms.openlocfilehash: c1972236e30be4e6ca738b606b00398f5c7860e0
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754866"
---
# <a name="compiler-warning-level-1-c4291"></a>Предупреждение компилятора (уровень 1) C4291

'декларация' : не найдено сопоставления оператора; память не будет освобождена, если инициализация бросает исключение

Используется [новое](../../cpp/new-operator-cpp.md) размещение, для которого нет [удаления](../../cpp/delete-operator-cpp.md)размещения.

Когда память выделяется для объекта с **новым**оператором, вызывается конструктор объекта. Если конструктор бросает исключение, любая память, которая была выделена для объекта, должна быть разобрана. Это не может иметь место, если не существует функция **удаления** оператора, которая соответствует **новому**оператору.

Если вы используете **новый** оператор без каких-либо дополнительных аргументов и компилируете с [/GX](../../build/reference/gx-enable-exception-handling.md), [/EHs](../../build/reference/eh-exception-handling-model.md), или /EHa варианты для включения обработки исключений, компилятор будет генерировать код для вызова оператора **удалить,** если конструктор бросает исключение.

Если вы используете форму размещения **нового** оператора (форма с аргументами в дополнение к размеру распределения) и конструктор объекта бросает исключение, компилятор будет по-прежнему генерировать код для вызова оператора **удалить;** но это будет делать это только в том случае, если форма размещения оператора **удаляется,** соответствующие форме размещения оператора **нового,** который выделил память. Пример:

```cpp
// C4291.cpp
// compile with: /EHsc /W1
#include <malloc.h>

class CList
{
public:
   CList(int)
   {
      throw "Fail!";
   }
};

void* operator new(size_t size, char* pszFilename, int nLine)
{
   return malloc(size);
}

int main(void)
{
   try
   {
      // This will call ::operator new(unsigned int) to allocate heap
      // memory. Heap memory pointed to by pList1 will automatically be
      // deallocated by a call to ::operator delete(void*) when
      // CList::CList(int) throws an exception.
      CList* pList1 = new CList(10);
   }
   catch (...)
   {
   }

   try
   {
      // This will call the overloaded ::operator new(size_t, char*, int)
      // to allocate heap memory. When CList::CList(int) throws an
      // exception, ::operator delete(void*, char*, int) should be called
      // to deallocate the memory pointed to by pList2. Since
      // ::operator delete(void*, char*, int) has not been implemented,
      // memory will be leaked when the deallocation cannot occur.
      CList* pList2 = new(__FILE__, __LINE__) CList(20);   // C4291
   }
   catch (...)
   {
   }
}
```

Вышеприведенный пример генерирует предупреждение C4291, потому что не была **определена** форма размещения оператора, которая соответствовала бы форме размещения **оператора.** Чтобы решить проблему, вставьте следующий код выше **основной**. Обратите внимание, что все перегруженные параметры функции **удаления** оператора совпадают с параметрами перегруженного **оператора,** за исключением первого параметра.

```cpp
void operator delete(void* pMem, char* pszFilename, int nLine)
{
   free(pMem);
}
```
