---
title: "Функция обратного вызова для CDC::EnumObjects | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- Callback Function for CDC::EnumObjects
dev_langs:
- C++
helpviewer_keywords:
- callback functions, for CDC::EnumObjects
ms.assetid: 380088b1-88a5-4fb4-bbb5-dd9e8386572b
caps.latest.revision: 10
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
ms.openlocfilehash: e4b24b5f5333d5514b9fdf69d204bca5d7947d7a
ms.lasthandoff: 02/24/2017

---
# <a name="callback-function-for-cdcenumobjects"></a>Функция обратного вызова для CDC::EnumObjects
*ObjectFunc* имя — это имя функции, предоставляемой приложением.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
int CALLBACK EXPORT ObjectFunc(
    LPSTR lpszLogObject,  
    LPSTR* lpData);
```  
  
#### <a name="parameters"></a>Параметры  
 *lpszLogObject*  
 Указывает [LOGPEN](../../mfc/reference/logpen-structure.md) или [LOGBRUSH](../../mfc/reference/logbrush-structure.md) структуру данных, содержащую сведения о логических атрибутов объекта.  
  
 `lpData`  
 Указывает на основе предоставленных приложением данных, передаваемый `EnumObjects` функции.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Функция обратного вызова возвращает `int`. Это возвращаемое значение определяется пользователем. Если функция обратного вызова возвращает 0, `EnumObjects` останавливает перечисления раньше.  
  
## <a name="remarks"></a>Примечания  
 Фактическое имя необходимо экспортировать.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxwin.h  
  
## <a name="see-also"></a>См. также  
 [Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDC::EnumObjects](../../mfc/reference/cdc-class.md#enumobjects)


