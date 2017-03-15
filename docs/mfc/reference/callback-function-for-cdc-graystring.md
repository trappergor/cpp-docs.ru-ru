---
title: "Функция обратного вызова для CDC::GrayString | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- Callback Function for CDC::GrayString
dev_langs:
- C++
helpviewer_keywords:
- callback functions, for CDC::GrayString
ms.assetid: 5217e183-df48-426b-931b-6245022ca36f
caps.latest.revision: 11
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 3ce3afefae9618420a8a97b27994c33604745677
ms.lasthandoff: 02/24/2017

---
# <a name="callback-function-for-cdcgraystring"></a>Функция обратного вызова для CDC::GrayString
*OutputFunc* — это имя функции обратного вызова, предоставляемую приложением.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
BOOL CALLBACK EXPORT OutputFunc(
    HDC hDC,  
    LPARAM lpData,  
    int nCount);
```  
  
#### <a name="parameters"></a>Параметры  
 `hDC`  
 Определяет контекст устройства памяти с растровым изображением, по меньшей мере ширину и высоту, определяемой `nWidth` и `nHeight` в `GrayString`.  
  
 `lpData`  
 Указывает на строку символов, которую необходимо нарисовать.  
  
 `nCount`  
 Указывает число символов для вывода.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращаемое значение функции обратного вызова должен быть **TRUE** в случае успеха; в противном случае это **FALSE**.  
  
## <a name="remarks"></a>Примечания  
 Функция обратного вызова (*OutputFunc*) должен рисования изображения относительно координат (0,0) вместо (*x*, *y*).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxwin.h  
  
## <a name="see-also"></a>См. также  
 [Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDC::GrayString](../../mfc/reference/cdc-class.md#graystring)


