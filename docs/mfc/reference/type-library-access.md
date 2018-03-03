---
title: "Введите доступ к библиотеке | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.macros
dev_langs:
- C++
helpviewer_keywords:
- type libraries [MFC], accessing
ms.assetid: a03fa7f0-86c2-4119-bf81-202916fb74b3
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: bbc5ceabe60d7ee15d85495bb1a431955a589849
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="type-library-access"></a>Доступ к библиотеке типов
Библиотеки типов предоставляют интерфейсы для других приложений, поддерживающих OLE элемента управления OLE. Каждый элемент управления OLE должны иметь библиотеку типов, если один или несколько интерфейсов, предоставляемых.  
  
 Следующие макросы разрешить элемента управления OLE для предоставления доступа к библиотеке типов:  
  
### <a name="type-library-access"></a>Доступ к библиотеке типов  
  
|||  
|-|-|  
|[DECLARE_OLETYPELIB](#declare_oletypelib)|Объявляет `GetTypeLib` функции-члене класса элемента управления OLE (следует использовать в объявлении класса).|  
|[IMPLEMENT_OLETYPELIB](#implement_oletypelib)|Реализует `GetTypeLib` функции-члене класса элемента управления OLE (следует использовать в реализацию класса).|  
  
##  <a name="declare_oletypelib"></a>DECLARE_OLETYPELIB  
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

##  <a name="implement_oletypelib"></a>IMPLEMENT_OLETYPELIB  
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
