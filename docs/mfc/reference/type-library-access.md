---
title: Доступ к библиотеке типов
ms.date: 11/04/2016
helpviewer_keywords:
- type libraries [MFC], accessing
ms.assetid: a03fa7f0-86c2-4119-bf81-202916fb74b3
ms.openlocfilehash: 23d4675bd3638d2effd1b967f0729f9e70dac6de
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2020
ms.locfileid: "78867041"
---
# <a name="type-library-access"></a>Доступ к библиотеке типов

Библиотеки типов предоставляют интерфейсы элемента управления OLE другим приложениям, поддерживающим технологию OLE. Каждый элемент управления OLE должен иметь библиотеку типов, если требуется предоставить один или несколько интерфейсов.

Следующие макросы позволяют элементу управления OLE предоставлять доступ к собственной библиотеке типов:

### <a name="type-library-access"></a>Доступ к библиотеке типов

|||
|-|-|
|[DECLARE_OLETYPELIB](#declare_oletypelib)|Объявляет функцию-член `GetTypeLib` элемента управления OLE (должна использоваться в объявлении класса).|
|[IMPLEMENT_OLETYPELIB](#implement_oletypelib)|Реализует функцию-член `GetTypeLib` элемента управления OLE (должна использоваться в реализации класса).|

##  <a name="declare_oletypelib"></a>DECLARE_OLETYPELIB

Объявляет функцию члена `GetTypeLib` класса Control.

```
DECLARE_OLETYPELIB(class_name)
```

### <a name="parameters"></a>Параметры

*class_name*<br/>
Имя класса элемента управления, связанного с библиотекой типов.

### <a name="remarks"></a>Remarks

Используйте этот макрос в файле заголовка класса элемента управления.

### <a name="requirements"></a>Требования

**Заголовок:** afxdisp.h

##  <a name="implement_oletypelib"></a>IMPLEMENT_OLETYPELIB

Реализует функцию члена `GetTypeLib` элемента управления.

```
IMPLEMENT_OLETYPELIB(class_name, tlid, wVerMajor,  wVerMinor)
```

### <a name="parameters"></a>Параметры

*class_name*<br/>
Имя класса элемента управления, связанного с библиотекой типов.

*тлид*<br/>
ИДЕНТИФИКАЦИОНный номер библиотеки типов.

*ввермажор*<br/>
Основной номер версии библиотеки типов.

*вверминор*<br/>
Дополнительный номер версии библиотеки типов.

### <a name="remarks"></a>Remarks

Этот макрос должен присутствовать в файле реализации для любого класса элементов управления, использующего макрос DECLARE_OLETYPELIB.

### <a name="requirements"></a>Требования

**Заголовок:** afxdisp.h

## <a name="see-also"></a>См. также раздел

[Макросы и глобальные](../../mfc/reference/mfc-macros-and-globals.md)
