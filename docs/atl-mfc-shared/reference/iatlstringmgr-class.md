---
title: Класс IAtlStringMgr
ms.date: 10/18/2018
f1_keywords:
- IAtlStringMgr
- ATLSIMPSTR/ATL::IAtlStringMgr
- ATLSIMPSTR/ATL::Allocate
- ATLSIMPSTR/ATL::Clone
- ATLSIMPSTR/ATL::Free
- ATLSIMPSTR/ATL::GetNilString
- ATLSIMPSTR/ATL::Reallocate
helpviewer_keywords:
- shared classes, IAtlStringMgr
- memory, managing
- IAtlStringMgr class
ms.assetid: 722f0346-a770-4aa7-8f94-177be8dba823
ms.openlocfilehash: 978d33c719b9cb8c2708dc97fa78874534dfd748
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/11/2019
ms.locfileid: "57749962"
---
# <a name="iatlstringmgr-class"></a>Класс IAtlStringMgr

Этот класс представляет интерфейс для `CStringT` диспетчера памяти.

## <a name="syntax"></a>Синтаксис

```
__interface IAtlStringMgr
```

## <a name="members"></a>Участники

### <a name="methods"></a>Методы

|||
|-|-|
|[выделить](#allocate)|Вызовите этот метод, чтобы выделить новую структуру данных строки.|
|[Clone](#clone)|Вызовите этот метод для возврата указателя на новый диспетчер строку для использования с другим экземпляром `CSimpleStringT`.|
|[бесплатно](#free)|Вызовите этот метод для освобождения структуру данных строки.|
|[GetNilString](#getnilstring)|Возвращает указатель на `CStringData` объект, используемый объектами, пустая строка.|
|[Перераспределение](#reallocate)|Вызовите этот метод для перераспределения структуру данных строки.|

## <a name="remarks"></a>Примечания

Этот интерфейс управляет памятью, используемые классами MFC независимый строки; Например, [CSimpleStringT](../../atl-mfc-shared/reference/csimplestringt-class.md), [CStringT](../../atl-mfc-shared/reference/cstringt-class.md), и [CFixedStringT](../../atl-mfc-shared/reference/cfixedstringt-class.md).

Этот класс позволяет реализовать диспетчер памяти для настраиваемой для класса настраиваемую строку. Дополнительные сведения см. в разделе [управление памятью и CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).

## <a name="requirements"></a>Требования

**Заголовок:** atlsimpstr.h

##  <a name="allocate"></a>  IAtlStringMgr::Allocate

Выделяет новую структуру данных строки.

```
CStringData* Allocate(int nAllocLength,int nCharSize) throw();
```

### <a name="parameters"></a>Параметры

*nAllocLength*<br/>
Число символов в новом блоке памяти.

*nCharSize*<br/>
Размер (в байтах) тип символа, используемый диспетчером строки.

### <a name="return-value"></a>Возвращаемое значение

Возвращает указатель на начало выделенного блока памяти.

> [!NOTE]
>  Ошибка выделения не сигнал путем создания исключения. Вместо этого ошибка выделения должны сигнализировать, возвращая значение NULL.

### <a name="remarks"></a>Примечания

Вызовите [IAtlStringMgr::Free](#free) или [IAtlStringMgr::ReAllocate](#reallocate) для освобождения памяти, выделенной с помощью этого метода.

> [!NOTE]
>  Примеры использования см. в разделе [управление памятью и CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).

##  <a name="clone"></a>  IAtlStringMgr::Clone

Возвращает указатель на новый диспетчер строку для использования с другим экземпляром `CSimpleStringT`.

```
IAtlStringMgr* Clone() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает копию объекта `IAtlStringMgr` объекта.

### <a name="remarks"></a>Примечания

Обычно вызывается платформой при необходимости диспетчера строк для новой строки. В большинстве случаев **это** возвращается указатель.

Тем не менее если диспетчер памяти не поддерживает используется несколько экземпляров `CSimpleStringT`, должны возвращаться указатель на диспетчер совместный доступ к строке.

> [!NOTE]
>  Примеры использования см. в разделе [управление памятью и CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).

##  <a name="free"></a>  IAtlStringMgr::Free

Освобождает структуру данных строки.

```
void Free(CStringData* pData) throw();
```

### <a name="parameters"></a>Параметры

*pData*<br/>
Указатель на блок памяти, который требуется освободить.

### <a name="remarks"></a>Примечания

Освобождает указанный блок памяти ранее выделенный методом [выделения](#allocate) или [перераспределения](../../atl/reference/iatlmemmgr-class.md#reallocate).

> [!NOTE]
>  Примеры использования см. в разделе [управление памятью и CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).

##  <a name="getnilstring"></a>  IAtlStringMgr::GetNilString

Возвращает указатель на структуру данных строка пустая строка.

```
CStringData* GetNilString() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на `CStringData` объект, используемый для представления пустая строка.

### <a name="remarks"></a>Примечания

Вызывайте эту функцию для возврата представления является пустая строка.

> [!NOTE]
> При реализации диспетчера пользовательская строка, эта функция никогда не должен завершаться ошибкой. Это можно обеспечить путем внедрения экземпляр `CNilStringData` в класс диспетчера строки и возвращают указатель на этот экземпляр.

> [!NOTE]
> Примеры использования см. в разделе [управление памятью и CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).

## <a name="reallocate"></a>  IAtlStringMgr::Reallocate

Перераспределяет структуру данных строки.

```
CStringData* Reallocate(
    CStringData* pData,
    int nAllocLength,
    int nCharSize) throw();
```

### <a name="parameters"></a>Параметры

*pData*<br/>
Указатель на память, выделенную ранее данным диспетчером памяти.

*nAllocLength*<br/>
Число символов в новом блоке памяти.

*nCharSize*<br/>
Размер (в байтах) тип символа, используемый диспетчером строки.

### <a name="return-value"></a>Возвращаемое значение

Возвращает указатель на начало выделенного блока памяти.

### <a name="remarks"></a>Примечания

Вызывайте эту функцию, чтобы изменить размер существующего блока памяти, определяемое *pData*.

Вызовите [IAtlStringMgr::Free](#free) для освобождения памяти, выделенной с помощью этого метода.

> [!NOTE]
> Примеры использования см. в разделе [управление памятью и CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).

## <a name="see-also"></a>См. также

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Общие классы ATL и MFC](../../atl-mfc-shared/atl-mfc-shared-classes.md)
