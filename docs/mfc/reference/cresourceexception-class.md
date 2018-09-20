---
title: Класс CResourceException | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CResourceException
- AFXWIN/CResourceException
- AFXWIN/CResourceException::CResourceException
dev_langs:
- C++
helpviewer_keywords:
- CResourceException [MFC], CResourceException
ms.assetid: af6ae043-d124-4bfd-b35e-7bb0db67d289
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 993b484c40386a60dd2da04d7198d692f5e16f97
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46445078"
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


