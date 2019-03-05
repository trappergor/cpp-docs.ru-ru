---
title: Класс CNotSupportedException
ms.date: 11/04/2016
f1_keywords:
- CNotSupportedException
- AFX/CNotSupportedException
- AFX/CNotSupportedException::CNotSupportedException
helpviewer_keywords:
- CNotSupportedException [MFC], CNotSupportedException
ms.assetid: e517391b-eb94-4c39-ae32-87b45bf7d624
ms.openlocfilehash: c3af508cd39e277ca4ae0a9aad5e639f66edc53b
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57294815"
---
# <a name="cnotsupportedexception-class"></a>Класс CNotSupportedException

Представляет исключение, являющееся результатом запроса неподдерживаемой возможности.

## <a name="syntax"></a>Синтаксис

```
class CNotSupportedException : public CSimpleException
```

## <a name="members"></a>Члены

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CNotSupportedException::CNotSupportedException](#cnotsupportedexception)|Создает объект `CNotSupportedException`.|

## <a name="remarks"></a>Примечания

Без дальнейшего уточнения невозможна и не требуется.

Дополнительные сведения об использовании `CNotSupportedException`, см. в статье [обработка исключений (MFC)](../../mfc/exception-handling-in-mfc.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CException](../../mfc/reference/cexception-class.md)

[CSimpleException](../../mfc/reference/csimpleexception-class.md)

`CNotSupportedException`

## <a name="requirements"></a>Требования

**Заголовок:** afx.h

##  <a name="cnotsupportedexception"></a>  CNotSupportedException::CNotSupportedException

Создает объект `CNotSupportedException`.

```
CNotSupportedException();
```

### <a name="remarks"></a>Примечания

Не используйте этот конструктор напрямую, но вместо этого вызовите глобальную функцию [AfxThrowNotSupportedException](exception-processing.md#afxthrownotsupportedexception). Дополнительные сведения об обработке исключений см. в статье [обработка исключений в MFC](../exception-handling-in-mfc.md).

## <a name="see-also"></a>См. также

[Класс CException](cexception-class.md)<br/>
[Диаграмма иерархии](../hierarchy-chart.md)
