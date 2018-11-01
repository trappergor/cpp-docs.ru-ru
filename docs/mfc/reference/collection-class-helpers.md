---
title: Вспомогательные функции классов коллекции
ms.date: 11/04/2016
f1_keywords:
- vc.mfc.macros.classes
helpviewer_keywords:
- DestructElements function
- ConstructElements function
- SerializeElements function
- collection classes [MFC], helper functions
- helper functions collection class [MFC]
ms.assetid: bc3a2368-9edd-4748-9e6a-13cba79517ca
ms.openlocfilehash: 639c4f7952abcf18c29aa3cb0d9fee45b50430af
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50567473"
---
# <a name="collection-class-helpers"></a>Вспомогательные функции классов коллекции

Классы коллекций `CMap`, `CList`, и `CArray` использовать Шаблонизированный вспомогательный объект глобальные функции для таких целей, как сравнение, копирования и сериализации элементов. Как часть реализации классов на основе `CMap`, `CList`, и `CArray`, необходимо переопределить эти функции, при необходимости с версиями, адаптированные к типу данных, хранящихся в карте, список или массив. Сведения о переопределении вспомогательные функции, такие как `SerializeElements`, см. в статье [коллекций: как сделать типобезопасных коллекций](../../mfc/how-to-make-a-type-safe-collection.md). Обратите внимание, что `ConstructElements` и `DestructElements` стали нерекомендуемыми.

Библиотеки Microsoft Foundation Class предоставляет следующие глобальные функции в afxtempl.h, которые помогут вам настроить пользовательские классы коллекций:

### <a name="collection-class-helpers"></a>Вспомогательные функции классов коллекции

|||
|-|-|
|[CompareElements](#compareelements)|Указывает, совпадают ли элементы.|
|[CopyElements](#copyelements)|Копирует элементы из одного массива в другой.|
|[DumpElements](#dumpelements)|Предоставляет поточно ориентированный выходных данных диагностики.|
|[HashKey](#hashkey)|Вычисляет хэш-ключа.|
|[SerializeElements](#serializeelements)|Сохраняет или извлекает элементы из архива или.|

##  <a name="compareelements"></a>  CompareElements

Вызывается непосредственно [CList::Find] (clist class.md #not_found.md #clist__find и косвенно посредством [cmap__lookup](cmap-class.md#lookup) и [cmap__operator &#91; &#93; ](cmap-class.md#operator_at).

```
template<class TYPE, class ARG_TYPE>
BOOL AFXAPI
CompareElements(
    const TYPE* pElement1,
    const ARG_TYPE* pElement2);
```

### <a name="parameters"></a>Параметры

*ТИП*<br/>
Тип первого элемента, который требуется сравнить.

*pElement1*<br/>
Указатель на первый элемент для сравнения.

*ARG_TYPE*<br/>
Тип второго элемента для сравнения.

*pElement2*<br/>
Указатель на второй элемент для сравнения.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если объект, на который указывает *pElement1* равен объекту, на которые указывают *pElement2*; в противном случае — 0.

### <a name="remarks"></a>Примечания

`CMap` Вызывает использование `CMap` параметров шаблона *ключ* и *ARG_KEY*.

Реализация по умолчанию возвращает результат сравнения объектов  *\*pElement1* и  *\*pElement2*. Переопределите эту функцию, чтобы он сравнивает элементы способом, который подходит для вашего приложения.

В языке C++ определены оператор сравнения ( `==`) для простых типов (**char**, **int**, **float**, и так далее), но не определяет оператор сравнения для классы и структуры. Если вы хотите использовать `CompareElements` или для создания экземпляра одного из классов коллекций, которые использует его, необходимо определить оператор сравнения или перегружать `CompareElements` с версией, которая возвращает соответствующие значения.

### <a name="requirements"></a>Требования

   **Заголовок:** afxtempl.h

##  <a name="copyelements"></a>  CopyElements

Эта функция вызывается напрямую с помощью [CArray::Append](carray-class.md#append) и [CArray::Copy](carray-class.md#copy).

```
template<class TYPE>
void AFXAPI CopyElements(
    TYPE* pDest,
    const TYPE* pSrc,
    INT_PTR nCount);
```

### <a name="parameters"></a>Параметры

*ТИП*<br/>
Параметр шаблона, указывающий тип элементов для копирования.

*pDest*<br/>
Указатель на место назначения, куда будут скопированы элементы.

*pSrc*<br/>
Указатель на место хранения копируемых элементов.

*nCount*<br/>
Число копируемых элементов.

### <a name="remarks"></a>Примечания

Реализация по умолчанию использует оператор простого присваивания ( **=** ) для выполнения операции копирования. Если тип копируемых нет перегруженного оператора =, то реализация по умолчанию выполняет побитовое копирование.

Сведения о реализации это и другие вспомогательные функции, см. в статье [коллекций: как сделать типобезопасных коллекций](../how-to-make-a-type-safe-collection.md).

### <a name="requirements"></a>Требования

  **Заголовок** afxtempl.h

##  <a name="dumpelements"></a>  DumpElements

Предоставляет поточно ориентированный диагностические данные в виде текста для элементов коллекции при переопределении.

```
template<class TYPE>
void  AFXAPI DumpElements(
    CDumpContext& dc,
    const TYPE* pElements,
    INT_PTR nCount);
```

### <a name="parameters"></a>Параметры

*dc*<br/>
Дамп контекста для дампа элементов.

*ТИП*<br/>
Параметр шаблона, указывающий тип элементов.

*pElements*<br/>
Указатель на элементы, которые будут выводиться.

*nCount*<br/>
Число элементов, чтобы создать дамп.

### <a name="remarks"></a>Примечания

`CArray::Dump`, `CList::Dump`, И `CMap::Dump` функции вызывают это, если глубина дампа больше 0.

Реализация по умолчанию не выполняет никаких действий. Если элементы коллекции являются производными от `CObject`, переопределение обычно перебора элементов коллекции, вызов `Dump` для каждого элемента, в свою очередь.

### <a name="requirements"></a>Требования

  **Заголовок** afxtempl.h

##  <a name="hashkey"></a>  HashKey

Вычисляет хэш-значение для указанного ключа.

```
template<class ARG_KEY>
AFX_INLINE UINT AFXAPI HashKey(ARG_KEY  key);
```

### <a name="parameters"></a>Параметры

*ARG_KEY*<br/>
Параметр шаблона, указывающий тип данных, используемый для доступа к ключа карты.

*key*<br/>
Ключ, значение которого хэш вычисляться.

### <a name="return-value"></a>Возвращаемое значение

Значение хэша ключа.

### <a name="remarks"></a>Примечания

Эта функция вызывается напрямую с помощью [CMap::RemoveKey](cmap-class.md#removekey) и косвенно посредством [CMap::Lookup](cmap-class.md#lookup) и [CMap::Operator &#91; &#93; ](cmap-class.md#operator_at).

Реализация по умолчанию создает хэш-значения путем перехода *ключ* на четыре позиции вправо. Переопределите эту функцию, чтобы он возвращал хэш-значений требуется для вашего приложения.

### <a name="example"></a>Пример

```cpp
template <> UINT AFXAPI HashKey(unsigned __int64 key)
{
   // Generate the hash value by XORing the lower 32 bits of the number
   // with the upper 32 bits
   return(UINT(key) ^ UINT(key >> 32));
}
```

### <a name="requirements"></a>Требования

  **Заголовок** afxtempl.h

##  <a name="serializeelements"></a>  SerializeElements

[CArray](carray-class.md), [CList](clist-class.md), и [CMap](cmap-class.md) вызывайте эту функцию для сериализации элементов.

```
template<class TYPE>
void AFXAPI SerializeElements(CArchive& ar, TYPE* pElements, INT_PTR nCount);
```

### <a name="parameters"></a>Параметры

*ТИП*<br/>
Параметр шаблона, указывающий тип элементов.

*ar*<br/>
Архивация с клиента или на объект архива.

*pElements*<br/>
Указатель элементов архивации.

*nCount*<br/>
Количество элементов архивации

### <a name="remarks"></a>Примечания

Реализация по умолчанию не побитовую операцию чтения или записи.

Сведения о реализации это и другие вспомогательные функции, см. в статье [коллекций: как сделать типобезопасных коллекций](../how-to-make-a-type-safe-collection.md).

### <a name="example"></a>Пример

См. пример в этой статье [коллекций: как сделать типобезопасных коллекций](../how-to-make-a-type-safe-collection.md).

### <a name="requirements"></a>Требования

  **Заголовок** afxtempl.h

## <a name="see-also"></a>См. также

[Макросы и глобальные объекты](mfc-macros-and-globals.md)<br/>
[Класс CMap](cmap-class.md)<br/>
[Класс CList](clist-class.md)<br/>
[Класс CArray](carray-class.md)