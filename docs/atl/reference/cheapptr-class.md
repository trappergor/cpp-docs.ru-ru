---
title: Класс CHeapPtr
ms.date: 11/04/2016
f1_keywords:
- CHeapPtr
- ATLCORE/ATL::CHeapPtr
- ATLCORE/ATL::CHeapPtr::CHeapPtr
- ATLCORE/ATL::CHeapPtr::Allocate
- ATLCORE/ATL::CHeapPtr::Reallocate
helpviewer_keywords:
- CHeapPtr class
ms.assetid: e5c5bfd4-9bf1-4164-8a83-8155fe253454
ms.openlocfilehash: 8cb35139e707d81a53edb762a2b7fc2ab41ff247
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57296063"
---
# <a name="cheapptr-class"></a>Класс CHeapPtr

Класс смарт-указатель для управления кучей указателей.

> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.

## <a name="syntax"></a>Синтаксис

```
template<typename T, class Allocator=CCRTAllocator>
class CHeapPtr : public CHeapPtrBase<T, Allocator>
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Тип объекта для сохранения в куче.

*Распределитель*<br/>
Класс выделения памяти для использования.

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CHeapPtr::CHeapPtr](#cheapptr)|Конструктор.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание:|
|----------|-----------------|
|[CHeapPtr::Allocate](#allocate)|Этот метод используется для выделения памяти в куче для хранения объектов.|
|[CHeapPtr::Reallocate](#reallocate)|Этот метод вызывается для повторного выделения памяти в куче.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание:|
|----------|-----------------|
|[CHeapPtr::operator =](#operator_eq)|Оператор присваивания.|

## <a name="remarks"></a>Примечания

`CHeapPtr` является производным от [CHeapPtrBase](../../atl/reference/cheapptrbase-class.md) и по умолчанию использует подпрограммы CRT (в [CCRTAllocator](../../atl/reference/ccrtallocator-class.md)) для выделения и освобождения памяти. Класс [CHeapPtrList](../../atl/reference/cheapptrlist-class.md) может использоваться для создания списка указателей кучи. См. также [CComHeapPtr](../../atl/reference/ccomheapptr-class.md), который использует процедуры выделения памяти для COM.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CHeapPtrBase](../../atl/reference/cheapptrbase-class.md)

`CHeapPtr`

## <a name="requirements"></a>Требования

**Заголовок:** файле atlcore.h

##  <a name="allocate"></a>  CHeapPtr::Allocate

Этот метод используется для выделения памяти в куче для хранения объектов.

```
bool Allocate(size_t nElements = 1) throw();
```

### <a name="parameters"></a>Параметры

*nElements*<br/>
Число элементов, используемых для вычисления объема памяти для выделения. Значение по умолчанию — 1.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение true, если память была успешно выделен, значение false в случае сбоя.

### <a name="remarks"></a>Примечания

Подпрограммы распределителя служат для резервирования недостаточно памяти в куче для хранения *nElement* объектов типа, определенного в конструкторе.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#77](../../atl/codesnippet/cpp/cheapptr-class_1.cpp)]

##  <a name="cheapptr"></a>  CHeapPtr::CHeapPtr

Конструктор.

```
CHeapPtr() throw();
explicit CHeapPtr(T* p) throw();
CHeapPtr(CHeapPtr<T, Allocator>& p) throw();
```

### <a name="parameters"></a>Параметры

*p*<br/>
Существующего указателя кучи или `CHeapPtr`.

### <a name="remarks"></a>Примечания

Указатель кучи при необходимости могут создаваться с использованием существующего указателя, или `CHeapPtr` объекта. Если Да, новый `CHeapPtr` объект несет ответственность за управление новый указатель и ресурсы.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#78](../../atl/codesnippet/cpp/cheapptr-class_2.cpp)]

##  <a name="operator_eq"></a>  CHeapPtr::operator =

Оператор присвоения.

```
CHeapPtr<T, Allocator>& operator=(
    CHeapPtr<T, Allocator>& p) throw();
```

### <a name="parameters"></a>Параметры

*p*<br/>
Существующий объект `CHeapPtr`.

### <a name="return-value"></a>Возвращаемое значение

Возвращает ссылку на обновленный `CHeapPtr`.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#80](../../atl/codesnippet/cpp/cheapptr-class_3.cpp)]

##  <a name="reallocate"></a>  CHeapPtr::Reallocate

Этот метод вызывается для повторного выделения памяти в куче.

```
bool Reallocate(size_t nElements) throw();
```

### <a name="parameters"></a>Параметры

*nElements*<br/>
Новый номер элементов, используемый для вычисления объема памяти для выделения.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение true, если память была успешно выделен, значение false в случае сбоя.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#79](../../atl/codesnippet/cpp/cheapptr-class_4.cpp)]

## <a name="see-also"></a>См. также

[Класс CHeapPtrBase](../../atl/reference/cheapptrbase-class.md)<br/>
[Класс CCRTAllocator](../../atl/reference/ccrtallocator-class.md)<br/>
[Общие сведения о классе](../../atl/atl-class-overview.md)
