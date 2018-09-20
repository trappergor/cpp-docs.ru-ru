---
title: Введите доступ к библиотеке | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.mfc.macros
dev_langs:
- C++
helpviewer_keywords:
- type libraries [MFC], accessing
ms.assetid: a03fa7f0-86c2-4119-bf81-202916fb74b3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1a361c1e50945b19562082424c178a21191bd0b9
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46404746"
---
# <a name="type-library-access"></a>Доступ к библиотеке типов

Библиотеки типов предоставить доступ к интерфейсам управления OLE для других приложений, поддерживающих OLE. Каждый элемент управления OLE должен иметь библиотеку типов, если один или несколько интерфейсов должны быть предоставлены.

Следующие макросы разрешить управления OLE для предоставления доступа к библиотеке типов:

### <a name="type-library-access"></a>Доступ к библиотеке типов

|||
|-|-|
|[DECLARE_OLETYPELIB](#declare_oletypelib)|Объявляет `GetTypeLib` функции-члена элемента управления OLE (необходимо использовать в объявлении класса).|
|[IMPLEMENT_OLETYPELIB](#implement_oletypelib)|Реализует `GetTypeLib` функции-члена элемента управления OLE (необходимо использовать в реализации класса).|

##  <a name="declare_oletypelib"></a>  DECLARE_OLETYPELIB

Объявляет `GetTypeLib` функция-член класса элемента управления.

```
DECLARE_OLETYPELIB(class_name)
```

### <a name="parameters"></a>Параметры

*class_name*<br/>
Имя класса элемента управления, относящиеся к библиотеке типов.

### <a name="remarks"></a>Примечания

Используйте этот макрос в файле заголовка класса элемента управления.

### <a name="requirements"></a>Требования

**Заголовок:** afxdisp.h

##  <a name="implement_oletypelib"></a>  IMPLEMENT_OLETYPELIB

Реализует элемент управления `GetTypeLib` функция-член.

```
IMPLEMENT_OLETYPELIB(class_name, tlid, wVerMajor,  wVerMinor)
```

### <a name="parameters"></a>Параметры

*class_name*<br/>
Имя класса элемента управления, относящиеся к библиотеке типов.

*tlid*<br/>
Идентификатор библиотеки типов.

*wVerMajor*<br/>
Номер основной номер версии библиотеки типов.

*wVerMinor*<br/>
Номера дополнительный номер версии библиотеки типов.

### <a name="remarks"></a>Примечания

Этот макрос должен указываться в файле реализации для любого класса элемента управления, который использует declare_oletypelib-макрос.

### <a name="requirements"></a>Требования

**Заголовок:** afxdisp.h

## <a name="see-also"></a>См. также

[Макросы и глобальные объекты](../../mfc/reference/mfc-macros-and-globals.md)
