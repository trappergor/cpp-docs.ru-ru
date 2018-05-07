---
title: Dhtmlurleventmapentry-структура | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- DHtmlUrlEventMapEntry
dev_langs:
- C++
helpviewer_keywords:
- DHtmlUrlEventMapEntry structure [MFC]
ms.assetid: 43117c1f-1a51-406c-aa2f-fea647080049
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d038fa188ac431f20b0b19ca8ad8bf675943954c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="dhtmlurleventmapentry-structure"></a>DHtmlUrlEventMapEntry Structure
`DHtmlUrlEventMapEntry` Структура обеспечивает поддержку сопоставления событий нескольких URL-адрес.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
struct DHtmlUrlEventMapEntry  
{  
LPCTSTR szUrl;  
const DHtmlEventMapEntry *pEventMap;  
};  
```  
  
#### <a name="parameters"></a>Параметры  
 `szUrl`  
 URL-адрес.  
  
 *pEventMap*  
 Схема событий, связанных с URL-адрес.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxdhtml.h  
  
## <a name="see-also"></a>См. также  
 [Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)

