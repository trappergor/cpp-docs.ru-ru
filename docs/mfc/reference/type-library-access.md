---
title: Доступ к библиотеке типов
ms.date: 11/04/2016
helpviewer_keywords:
- type libraries [MFC], accessing
ms.assetid: a03fa7f0-86c2-4119-bf81-202916fb74b3
ms.openlocfilehash: 1794e16489ab48d919bbd4116588fba4b74b88d9
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372877"
---
# <a name="type-library-access"></a>Доступ к библиотеке типов

Библиотеки типа разоблачают интерфейсы управления OLE другим приложениям, осведомленным о OLE. Каждый элемент управления OLE должен иметь библиотеку типов, если один или несколько интерфейсов должны быть выставлены.

Следующие макросы позволяют элементу управления OLE обеспечить доступ к собственной библиотеке типов:

### <a name="type-library-access"></a>Доступ к библиотеке типов

|||
|-|-|
|[DECLARE_OLETYPELIB](#declare_oletypelib)|Объявляет функцию `GetTypeLib` элемента управления OLE (должна использоваться в декларации класса).|
|[IMPLEMENT_OLETYPELIB](#implement_oletypelib)|Реализует функцию `GetTypeLib` элемента управления OLE (должен использоваться в реализации класса).|

## <a name="declare_oletypelib"></a><a name="declare_oletypelib"></a>DECLARE_OLETYPELIB

Объявляет функцию `GetTypeLib` участника вашего класса управления.

```
DECLARE_OLETYPELIB(class_name)
```

### <a name="parameters"></a>Параметры

*class_name*<br/>
Название класса управления, относящееся к библиотеке типов.

### <a name="remarks"></a>Remarks

Используйте этот макрос в файле заголовка заголовка класса управления.

### <a name="requirements"></a>Требования

**Заголовок:** afxdisp.h

## <a name="implement_oletypelib"></a><a name="implement_oletypelib"></a>IMPLEMENT_OLETYPELIB

Реализует функцию элемента элемента `GetTypeLib` управления.

```
IMPLEMENT_OLETYPELIB(class_name, tlid, wVerMajor,  wVerMinor)
```

### <a name="parameters"></a>Параметры

*class_name*<br/>
Название класса управления, относящееся к библиотеке типов.

*tlid*<br/>
Идентификационный номер библиотеки типа.

*wVerMajor*<br/>
Номер основной версии библиотеки типа.

*wVerMinor*<br/>
Номер незначительной версии библиотеки типа.

### <a name="remarks"></a>Remarks

Этот макрос должен отображаться в файле реализации для любого класса управления, использующем у DECLARE_OLETYPELIB макроса.

### <a name="requirements"></a>Требования

**Заголовок:** afxdisp.h

## <a name="see-also"></a>См. также раздел

[Макросы и глобальные объекты](../../mfc/reference/mfc-macros-and-globals.md)
