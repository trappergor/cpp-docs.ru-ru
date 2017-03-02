---
title: "Функция обратного вызова для CDC::SetAbortProc | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- Callback Function for CDC::SetAbortProc
dev_langs:
- C++
helpviewer_keywords:
- callback functions, for CDC::SetAbortProc
ms.assetid: daa36d5d-15de-40fc-8d37-a865d06c4710
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
ms.openlocfilehash: 1ba16ea60d8b18abd1962ded2da7e11ff2ef09a1
ms.lasthandoff: 02/24/2017

---
# <a name="callback-function-for-cdcsetabortproc"></a>Функция обратного вызова для CDC::SetAbortProc
Имя *AbortFunc* — это имя функции, предоставляемой приложением.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
BOOL CALLBACK EXPORT AbortFunc(
    HDC hPr,  
    int code);
```  
  
#### <a name="parameters"></a>Параметры  
 *hPr*  
 Определяет контекст устройства.  
  
 `code`  
 Указывает, является ли ошибка. Оно равно 0, если ошибки не произошло. Это **SP_OUTOFDISK** Если диспетчер печати находится свободного дискового пространства и больше места на диске станет доступной, если приложение ожидает. Если `code` — **SP_OUTOFDISK**, приложения не требуется прервать задание печати. Если нет, он должен уступить диспетчера печати путем вызова **PeekMessage** или **GetMessage** функции Windows.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращаемое значение функции обработчика прерывания ненулевым, если задание печати для продолжения и 0 после отмены.  
  
## <a name="remarks"></a>Примечания  
 Фактическое имя необходимо экспортировать, как описано в подразделе "Примечания" [CDC::SetAbortProc](../../mfc/reference/cdc-class.md#setabortproc).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxwin.h  
  
## <a name="see-also"></a>См. также  
 [Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDC::SETABORTPROC](../../mfc/reference/cdc-class.md#setabortproc)


