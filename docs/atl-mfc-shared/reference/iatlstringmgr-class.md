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
ms.openlocfilehash: c3fabb7a7a6da4129787d219bd83b2a35fa0c4dd
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81746607"
---
# <a name="iatlstringmgr-class"></a>Класс IAtlStringMgr

Этот класс представляет интерфейс `CStringT` для менеджера памяти.

## <a name="syntax"></a>Синтаксис

```
__interface IAtlStringMgr
```

## <a name="members"></a>Участники

### <a name="methods"></a>Методы

|||
|-|-|
|[Выделить](#allocate)|Вызовите этот метод, чтобы выделить новую структуру данных строки.|
|[Clone](#clone) (Клонировать)|Вызов используйте этот метод, чтобы вернуть указатель новому `CSimpleStringT`менеджеру строки для использования в другом экземпляре.|
|[Бесплатный](#free)|Вызовите этот метод, чтобы освободить структуру данных строки.|
|[GetNilString](#getnilstring)|Возвращает указатель объекту, используемому `CStringData` пустыми объектами строки.|
|[Перераспределить](#reallocate)|Вызовите этот метод, чтобы перераспределить структуру данных строки.|

## <a name="remarks"></a>Remarks

Этот интерфейс управляет памятью, используемой классами строк MFC, независимыми от MFC; таких как [CSimpleStringT](../../atl-mfc-shared/reference/csimplestringt-class.md), [CStringT](../../atl-mfc-shared/reference/cstringt-class.md)и [CFixedStringT](../../atl-mfc-shared/reference/cfixedstringt-class.md).

Вы также можете использовать этот класс для реализации пользовательского менеджера памяти для пользовательского класса строк. Для получения дополнительной информации [см.](../../atl-mfc-shared/memory-management-with-cstringt.md)

## <a name="requirements"></a>Требования

**Заголовок:** atlsimpstr.h

## <a name="iatlstringmgrallocate"></a><a name="allocate"></a>IAtlStringMgr:Распределение

Выделяет новую структуру данных строки.

```
CStringData* Allocate(int nAllocLength,int nCharSize) throw();
```

### <a name="parameters"></a>Параметры

*nAllocДлина*<br/>
Количество символов в новом блоке памяти.

*nCharSize*<br/>
Размер (в байтах) типа символов, используемый диспетчером строки.

### <a name="return-value"></a>Возвращаемое значение

Возвращает указатель на начало выделенного блока памяти.

> [!NOTE]
> Не сигнализить о неудачном распределении, бросая исключение. Вместо этого, неудачное распределение должно быть сигнализировано путем возвращения NULL.

### <a name="remarks"></a>Remarks

Позвоните [iAtlStringMgr::Free](#free) или [IAtlStringMgr::Перераспределите,](#reallocate) чтобы освободить память, выделенную этим методом.

> [!NOTE]
> Примеры использования приведены в примерах [управления памятью и CStringT.](../../atl-mfc-shared/memory-management-with-cstringt.md)

## <a name="iatlstringmgrclone"></a><a name="clone"></a>IAtlStringMgr:Клон

Возвращает указатель новому менеджеру строки для `CSimpleStringT`использования в другом экземпляре.

```
IAtlStringMgr* Clone() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает копию объекта `IAtlStringMgr`.

### <a name="remarks"></a>Remarks

Обычно вызывается инфраструктурой, когда диспетчер строки необходим для новой строки. В большинстве случаев **этот** указатель возвращается.

Однако, если менеджер памяти не поддерживает, `CSimpleStringT`используемый несколькими экземплярами, указатель на менеджер строки sharable должен быть возвращен.

> [!NOTE]
> Примеры использования приведены в примерах [управления памятью и CStringT.](../../atl-mfc-shared/memory-management-with-cstringt.md)

## <a name="iatlstringmgrfree"></a><a name="free"></a>IAtlStringMgr::Бесплатно

Освобождает структуру данных строки.

```cpp
void Free(CStringData* pData) throw();
```

### <a name="parameters"></a>Параметры

*Pdata*<br/>
Указатель на блок памяти, чтобы быть освобождены.

### <a name="remarks"></a>Remarks

Освобождает указанный блок памяти, ранее выделенный [Выделением](#allocate) или [перераспределить.](../../atl/reference/iatlmemmgr-class.md#reallocate)

> [!NOTE]
> Примеры использования приведены в примерах [управления памятью и CStringT.](../../atl-mfc-shared/memory-management-with-cstringt.md)

## <a name="iatlstringmgrgetnilstring"></a><a name="getnilstring"></a>IAtlStringMgr::GetNilString

Возвращает указатель в структуру данных строки для пустой строки.

```
CStringData* GetNilString() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на `CStringData` объект, используемый для представления пустой строки.

### <a name="remarks"></a>Remarks

Вызовите эту функцию, чтобы вернуть представление пустой строки.

> [!NOTE]
> При реализации пользовательского диспетчера строк эта функция никогда не должна подводить неудачу. Это можно обеспечить, встраиввв экземпляр `CNilStringData` в класс диспетчера строки, и вернуть указатель в этот экземпляр.

> [!NOTE]
> Примеры использования приведены в примерах [управления памятью и CStringT.](../../atl-mfc-shared/memory-management-with-cstringt.md)

## <a name="iatlstringmgrreallocate"></a><a name="reallocate"></a>IAtlStringMgr:Перераспределить

Перераспределяет структуру данных строки.

```
CStringData* Reallocate(
    CStringData* pData,
    int nAllocLength,
    int nCharSize) throw();
```

### <a name="parameters"></a>Параметры

*Pdata*<br/>
Указатель на память, ранее выделенную этим менеджером памяти.

*nAllocДлина*<br/>
Количество символов в новом блоке памяти.

*nCharSize*<br/>
Размер (в байтах) типа символов, используемый диспетчером строки.

### <a name="return-value"></a>Возвращаемое значение

Возвращает указатель на начало выделенного блока памяти.

### <a name="remarks"></a>Remarks

Вызовите эту функцию, чтобы изменить размер существующего блока памяти, указанного *pData.*

Позвоните [iAtlStringMgr::Бесплатно](#free) освободить память, выделенную этим методом.

> [!NOTE]
> Примеры использования приведены в примерах [управления памятью и CStringT.](../../atl-mfc-shared/memory-management-with-cstringt.md)

## <a name="see-also"></a>См. также раздел

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Общие классы ATL/MFC](../../atl-mfc-shared/atl-mfc-shared-classes.md)
