---
title: Вспомогательные функции классов коллекции
ms.date: 11/04/2016
helpviewer_keywords:
- DestructElements function
- ConstructElements function
- SerializeElements function
- collection classes [MFC], helper functions
- helper functions collection class [MFC]
ms.assetid: bc3a2368-9edd-4748-9e6a-13cba79517ca
ms.openlocfilehash: 05fe49a4d8e6de92c584d40f3871f3efb906c7c8
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374814"
---
# <a name="collection-class-helpers"></a>Вспомогательные функции классов коллекции

Классы `CMap` `CList`коллекции `CArray` и используют шаблонные функции глобального помощника для таких целей, как сравнение, копирование и сериализация элементов. В рамках реализации классов `CMap`на `CList`основе, и, `CArray`вы должны переопределить эти функции по мере необходимости с версиями с учетом типа данных, хранящихся в карте, список или массив. Для получения информации о главных функций помощника, таких как `SerializeElements`, см. [Collections: How to Make a Type-Safe Collection](../../mfc/how-to-make-a-type-safe-collection.md) Обратите `ConstructElements` внимание, что и `DestructElements` были уволены.

Библиотека класса Фонда Майкрософт предоставляет следующие глобальные функции в afxtempl.h, чтобы помочь вам настроить классы коллекций:

### <a name="collection-class-helpers"></a>Вспомогательные функции классов коллекции

|||
|-|-|
|[CompareElements](#compareelements)|Указывает, являются ли элементы одинаковыми.|
|[CopyElements](#copyelements)|Копирует элементы из одного массива в другой.|
|[DumpElements](#dumpelements)|Обеспечивает потоково-ориентированный диагностический выход.|
|[ХэшКей](#hashkey)|Вычисляет ключ хэша.|
|[SerializeElements](#serializeelements)|Хранит или извлекает элементы в архив или из нее.|

## <a name="compareelements"></a><a name="compareelements"></a>СравнитеЭлементы

Вызывается непосредственно по ссылке «CList::Find» (clist-class.md'not_found.md-clist__find и косвенно [cmap__lookup](cmap-class.md#lookup) и [cmap__operator &#91;&#93;](cmap-class.md#operator_at).

```
template<class TYPE, class ARG_TYPE>
BOOL AFXAPI
CompareElements(
    const TYPE* pElement1,
    const ARG_TYPE* pElement2);
```

### <a name="parameters"></a>Параметры

*ТИП*<br/>
Тип первого элемента для сопоставления.

*pElement1*<br/>
Указатель на первый элемент для сопоставления.

*ARG_TYPE*<br/>
Тип второго элемента для сопоставления.

*pElement2*<br/>
Указатель на второй элемент для сопоставления.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если объект, на который указывает *pElement1,* равен объекту, на который указывает *pElement2;* в противном случае 0.

### <a name="remarks"></a>Remarks

Вызовы `CMap` используют `CMap` параметры шаблона *KEY* и *ARG_KEY.*

Реализация по умолчанию возвращает результат сравнения * \*pElement1* и * \*pElement2.* Переопределить эту функцию так, чтобы она сравнивала элементы таким образом, чтобы это было подходящим для вашего приложения.

Язык СЗ определяет оператора сравнения `==`() для простых типов **(char,** **int,** **float**и так далее), но не определяет оператора сравнения для классов и структур. Если вы хотите `CompareElements` использовать или мгновенно использовать один из классов коллекции, который использует его, `CompareElements` вы должны либо определить оператора сравнения или перегрузки с версией, которая возвращает соответствующие значения.

### <a name="requirements"></a>Требования

   **Заголовок:** afxtempl.h

## <a name="copyelements"></a><a name="copyelements"></a>CopyElements

Эта функция называется непосредственно [CArray::Append](carray-class.md#append) и [CArray::Copy](carray-class.md#copy).

```
template<class TYPE>
void AFXAPI CopyElements(
    TYPE* pDest,
    const TYPE* pSrc,
    INT_PTR nCount);
```

### <a name="parameters"></a>Параметры

*ТИП*<br/>
Параметры шаблона, определяющие тип элементов, которые будут скопированы.

*pDest*<br/>
Указатель к месту назначения, где элементы будут скопированы.

*Psrc*<br/>
Указатель на источник элементов, которые должны быть скопированы.

*Ncount*<br/>
Количество элементов, которые необходимо скопировать.

### <a name="remarks"></a>Remarks

Реализация по умолчанию использует **=** простого оператора назначения () для выполнения операции копирования. Если скопированный тип не имеет перегруженного оператора, то реализация по умолчанию выполняет битную копию.

Для получения информации о реализации этой и других функций помощника, [см.](../how-to-make-a-type-safe-collection.md)

### <a name="requirements"></a>Требования

  **Заголовок** afxtempl.h

## <a name="dumpelements"></a><a name="dumpelements"></a>DumpElements

Обеспечивает потоково-ориентированный диагностический выход в текстовой форме для элементов вашей коллекции при переориентации.

```
template<class TYPE>
void  AFXAPI DumpElements(
    CDumpContext& dc,
    const TYPE* pElements,
    INT_PTR nCount);
```

### <a name="parameters"></a>Параметры

*Dc*<br/>
Контекст свалки для элементов сброса.

*ТИП*<br/>
Параметры шаблона, определяющие тип элементов.

*pElements*<br/>
Указатель на элементы, которые должны быть сброшены.

*Ncount*<br/>
Количество элементов, которые должны быть сброшены.

### <a name="remarks"></a>Remarks

`CArray::Dump`Функции `CList::Dump`, `CMap::Dump` и функции называют это, если глубина дампа больше, чем 0.

Реализация по умолчанию не выполняет никаких действий. Если элементы вашей коллекции `CObject`получены из, то переопределение обычно будет итерироваться через элементы коллекции, требуя `Dump` для каждого элемента в свою очередь.

### <a name="requirements"></a>Требования

  **Заголовок** afxtempl.h

## <a name="hashkey"></a><a name="hashkey"></a>ХэшКей

Вычисляет значение хэша для данного ключа.

```
template<class ARG_KEY>
AFX_INLINE UINT AFXAPI HashKey(ARG_KEY  key);
```

### <a name="parameters"></a>Параметры

*ARG_KEY*<br/>
Параметры шаблона, определяющие тип данных, используемый для доступа к ключам карты.

*Ключ*<br/>
Ключ, стоимость хэша которого должна быть рассчитана.

### <a name="return-value"></a>Возвращаемое значение

Значение хэша ключа.

### <a name="remarks"></a>Remarks

Эта функция называется непосредственно [CMap::RemoveKey](cmap-class.md#removekey) и косвенно [CMap::Lookup](cmap-class.md#lookup) и [CMap::Оператор &#91;&#93;](cmap-class.md#operator_at).

Реализация по умолчанию создает значение хэша, перемещая *право ключа* на четыре позиции. Переопределить эту функцию так, чтобы она возвращала значения хэша, подходящие для приложения.

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

## <a name="serializeelements"></a><a name="serializeelements"></a>SerializeElements

[CArray,](carray-class.md) [CList](clist-class.md)и [CMap](cmap-class.md) называют эту функцию сериализуемой.

```
template<class TYPE>
void AFXAPI SerializeElements(CArchive& ar, TYPE* pElements, INT_PTR nCount);
```

### <a name="parameters"></a>Параметры

*ТИП*<br/>
Параметры шаблона, определяющие тип элементов.

*ar*<br/>
Архивный объект для архива в или из.

*pElements*<br/>
Указатель на архивированные элементы.

*Ncount*<br/>
Количество архивных элементов

### <a name="remarks"></a>Remarks

Реализация по умолчанию выполняет битовую прочтение или запись.

Для получения информации о реализации этой и других функций помощника, [см.](../how-to-make-a-type-safe-collection.md)

### <a name="example"></a>Пример

Смотрите пример в статье [Коллекции: Как сделать тип-безопасной коллекции](../how-to-make-a-type-safe-collection.md).

### <a name="requirements"></a>Требования

  **Заголовок** afxtempl.h

## <a name="see-also"></a>См. также раздел

[Макросы и глобальные объекты](mfc-macros-and-globals.md)<br/>
[Класс CMap](cmap-class.md)<br/>
[Класс CList](clist-class.md)<br/>
[Класс CArray](carray-class.md)
