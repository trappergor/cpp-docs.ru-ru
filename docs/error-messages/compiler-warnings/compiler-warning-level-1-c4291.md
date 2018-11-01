---
title: Предупреждение компилятора (уровень 1) C4291
ms.date: 11/04/2016
f1_keywords:
- C4291
helpviewer_keywords:
- C4291
ms.assetid: c2b95dea-38f2-4609-9104-707c30798da4
ms.openlocfilehash: e1b787e7149afe93fb50cc1e6ceaecba2e787876
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50465563"
---
# <a name="compiler-warning-level-1-c4291"></a>Предупреждение компилятора (уровень 1) C4291

«объявление»: не обнаружен; соответствующий оператор delete память не должна освобождаться при возникновении исключения инициализации

Размещение [новый](../../cpp/new-operator-cpp.md) используется для которого существует не размещения [удалить](../../cpp/delete-operator-cpp.md).

Если выделить память для объекта с помощью оператора **новый**, вызывается конструктор объекта. Если конструктор вызывает исключение, должна быть освобождена память, выделенная для объекта. Это не может иметь место, если оператор **удалить** функция существует, соответствующий оператор **новый**.

Если вы используете оператор **новый** без дополнительных аргументов и компиляции с [/GX](../../build/reference/gx-enable-exception-handling.md), [/EHs](../../build/reference/eh-exception-handling-model.md), или параметры/EHa на необходимость обработки исключений, компилятор создаст код Вызовите оператор **удалить** Если конструктор вызывает исключение.

При использовании формы размещения **новый** оператор (формы с аргументами в дополнение к размеру выделения) и конструктор объекта вызывает исключение, компилятор будет продолжать вызывать код, вызывающий оператор **удалить**; но она будет делать только если формы размещения оператора **удалить** существует сопоставление формы размещения оператора **новый** , выделена память. Пример:

```
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

Приведенный выше пример формирует предупреждение C4291, так как нет формы размещения оператора **удалить** был определен, соответствующий формы размещения оператора **новый**. Чтобы решить проблему, вставьте следующий код выше **основной**. Обратите внимание, что все перегруженный оператор **удалить** параметры функции соответствуют перегруженный оператор **новый**, за исключением первого параметра.

```
void operator delete(void* pMem, char* pszFilename, int nLine)
{
   free(pMem);
}
```