---
title: Введите доступ к библиотеке | Документы Microsoft
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
ms.openlocfilehash: fb81a8aa7d9262992da29a2d93cf770fad754316
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33373215"
---
# <a name="type-library-access"></a>Доступ к библиотеке типов
Библиотеки типов предоставляют интерфейсы для других приложений, поддерживающих OLE элемента управления OLE. Каждый элемент управления OLE должны иметь библиотеку типов, если один или несколько интерфейсов, предоставляемых.  
  
 Следующие макросы разрешить элемента управления OLE для предоставления доступа к библиотеке типов:  
  
### <a name="type-library-access"></a>Доступ к библиотеке типов  
  
|||  
|-|-|  
|[DECLARE_OLETYPELIB](#declare_oletypelib)|Объявляет `GetTypeLib` функции-члене класса элемента управления OLE (следует использовать в объявлении класса).|  
|[IMPLEMENT_OLETYPELIB](#implement_oletypelib)|Реализует `GetTypeLib` функции-члене класса элемента управления OLE (следует использовать в реализацию класса).|  
  
##  <a name="declare_oletypelib"></a>  DECLARE_OLETYPELIB  
 Объявляет `GetTypeLib` функции-члена класса элемента управления.  
  
```   
DECLARE_OLETYPELIB(class_name)   
```  
  
### <a name="parameters"></a>Параметры  
 *class_name*  
 Имя класса элемента управления, относящиеся к библиотеке типов.  
  
### <a name="remarks"></a>Примечания  
 Используйте этот макрос в файле заголовка для класса элемента управления.  

### <a name="requirements"></a>Требования  
 **Заголовок:** afxdisp.h  

##  <a name="implement_oletypelib"></a>  IMPLEMENT_OLETYPELIB  
 Реализует элемент управления `GetTypeLib` функции-члена.  
  
```   
IMPLEMENT_OLETYPELIB(class_name, tlid, wVerMajor,  wVerMinor)   
```  
  
### <a name="parameters"></a>Параметры  
 *class_name*  
 Имя класса элемента управления, относящиеся к библиотеке типов.  
  
 *tlid*  
 Идентификатор библиотеки типов.  
  
 `wVerMajor`  
 Номер основной версии библиотеки типов.  
  
 `wVerMinor`  
 Номера дополнительный номер версии библиотеки типов.  
  
### <a name="remarks"></a>Примечания  
 Этот макрос должен указываться в файле реализации для любого класса элемента управления, который использует `DECLARE_OLETYPELIB` макрос.  

### <a name="requirements"></a>Требования  
 **Заголовок:** afxdisp.h  
   
## <a name="see-also"></a>См. также  
 [Макросы и глобальные объекты](../../mfc/reference/mfc-macros-and-globals.md)
