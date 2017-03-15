---
title: "Введите доступ к библиотеке | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.macros
dev_langs:
- C++
helpviewer_keywords:
- type libraries, accessing
ms.assetid: a03fa7f0-86c2-4119-bf81-202916fb74b3
caps.latest.revision: 14
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 17a158366f94d27b7a46917282425d652e6b9042
ms.openlocfilehash: 8a3fbcf66036ef3df3bd34b5182dac8af3dfccef
ms.lasthandoff: 02/24/2017

---
# <a name="type-library-access"></a>Доступ к библиотеке типов
Библиотеки типов предоставления интерфейсов элемента управления OLE других OLE-совместимых приложений. Если один или несколько интерфейсов, предоставляемых каждого элемента управления OLE необходимо иметь библиотеку типов.  
  
 Следующие макросы разрешить элемента управления OLE для предоставления доступа к библиотеке типов.  
  
### <a name="type-library-access"></a>Доступ к библиотеке типов  
  
|||  
|-|-|  
|[DECLARE_OLETYPELIB](#declare_oletypelib)|Объявляет `GetTypeLib` функции-члены элемента управления OLE (необходимо использовать в объявлении класса).|  
|[IMPLEMENT_OLETYPELIB](#implement_oletypelib)|Реализует `GetTypeLib` функции-члены элемента управления OLE (необходимо использовать реализацию класса).|  
  
##  <a name="a-namedeclareoletypeliba--declareoletypelib"></a><a name="declare_oletypelib"></a>DECLARE_OLETYPELIB  
 Объявляет `GetTypeLib` функции-члена класса элемента управления.  
  
```   
DECLARE_OLETYPELIB(class_name)   
```  
  
### <a name="parameters"></a>Параметры  
 *class_name*  
 Имя класса элемента управления, относящиеся к библиотеке типов.  
  
### <a name="remarks"></a>Примечания  
 Используйте этот макрос в файле заголовка класса элемента управления.  

### <a name="requirements"></a>Требования  
 **Заголовок:** afxdisp.h  

##  <a name="a-nameimplementoletypeliba--implementoletypelib"></a><a name="implement_oletypelib"></a>IMPLEMENT_OLETYPELIB  
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
 Номер вспомогательной версии библиотеки типов.  
  
### <a name="remarks"></a>Примечания  
 Этот макрос должен присутствовать в файле реализации для любого класса элемента управления, который использует `DECLARE_OLETYPELIB` макрос.  

### <a name="requirements"></a>Требования  
 **Заголовок:** afxdisp.h  
   
## <a name="see-also"></a>См. также  
 [Макросы и глобальные объекты](../../mfc/reference/mfc-macros-and-globals.md)

