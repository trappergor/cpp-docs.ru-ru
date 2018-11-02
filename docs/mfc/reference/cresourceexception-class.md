---
title: Класс CResourceException
ms.date: 11/04/2016
f1_keywords:
- CResourceException
- AFXWIN/CResourceException
- AFXWIN/CResourceException::CResourceException
helpviewer_keywords:
- CResourceException [MFC], CResourceException
ms.assetid: af6ae043-d124-4bfd-b35e-7bb0db67d289
ms.openlocfilehash: aa7fd6e2caa15a256cec2eae5ede6c6e47cd1518
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50632700"
---
# <a name="cresourceexception-class"></a>Класс CResourceException

Генерируется, когда Windows не может найти или выбрать запрошенный ресурс.

## <a name="syntax"></a>Синтаксис

```
class CResourceException : public CSimpleException
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CResourceException::CResourceException](#cresourceexception)|Создает объект `CResourceException`.|

## <a name="remarks"></a>Примечания

Без дальнейшего уточнения невозможна и не требуется.

Дополнительные сведения об использовании `CResourceException`, см. в статье [обработка исключений (MFC)](../../mfc/exception-handling-in-mfc.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CException](../../mfc/reference/cexception-class.md)

[CSimpleException](../../mfc/reference/csimpleexception-class.md)

`CResourceException`

## <a name="requirements"></a>Требования

**Заголовок:** afxwin.h

##  <a name="cresourceexception"></a>  CResourceException::CResourceException

Создает объект `CResourceException`.

```
CResourceException();
```

### <a name="remarks"></a>Примечания

Не используйте этот конструктор напрямую, но вместо этого вызовите глобальную функцию [AfxThrowResourceException](exception-processing.md#afxthrowresourceexception). Дополнительные сведения об исключениях см. в статье [обработка исключений в MFC](../exception-handling-in-mfc.md).

## <a name="see-also"></a>См. также

[Класс CException](cexception-class.md)<br/>
[Диаграмма иерархии](../hierarchy-chart.md)

