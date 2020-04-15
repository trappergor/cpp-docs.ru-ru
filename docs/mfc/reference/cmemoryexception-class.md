---
title: Класс CMemoryException
ms.date: 11/04/2016
f1_keywords:
- CMemoryException
- AFX/CMemoryException
- AFX/CMemoryException::CMemoryException
helpviewer_keywords:
- CMemoryException [MFC], CMemoryException
ms.assetid: 9af0ed57-d12a-45ca-82b5-c910a60f7edf
ms.openlocfilehash: 375b4227a25ae4c18cfd263eff4c3ec13f1304e1
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370006"
---
# <a name="cmemoryexception-class"></a>Класс CMemoryException

Представляет условие исключения вне памяти.

## <a name="syntax"></a>Синтаксис

```
class CMemoryException : public CSimpleException
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CMemoryИсключение::Память Исключение](#cmemoryexception)|Формирует объект `CMemoryException`.|

## <a name="remarks"></a>Remarks

Никакая дальнейшая квалификация не требуется или невозможна. Исключения памяти автоматически выбрасываются **новым**. Если вы пишете свои `malloc`собственные функции памяти, используя, например, то вы несете ответственность за бросание исключений памяти.

Для получения `CMemoryException`дополнительной информации о , см. [Exception Handling (MFC)](../../mfc/exception-handling-in-mfc.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CException](../../mfc/reference/cexception-class.md)

[CSimpleException](../../mfc/reference/csimpleexception-class.md)

`CMemoryException`

## <a name="requirements"></a>Требования

**Заголовок:** afx.h

## <a name="cmemoryexceptioncmemoryexception"></a><a name="cmemoryexception"></a>CMemoryИсключение::Память Исключение

Формирует объект `CMemoryException`.

```
CMemoryException();
```

### <a name="remarks"></a>Remarks

Не используйте этот конструктор напрямую, а скорее позвоните в глобальную функцию [AfxThrowMemory.](exception-processing.md#afxthrowmemoryexception) эта глобальная функция может преуспеть в ситуации вне памяти, поскольку она строит объект исключения в ранее выделенной памяти. для получения дополнительной [информации](../exception-handling-in-mfc.md)об обработке исключений см.

## <a name="see-also"></a>См. также раздел

[Класс CException](cexception-class.md)<br/>
[Диаграмма иерархии](../hierarchy-chart.md)
