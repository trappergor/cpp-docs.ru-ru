---
title: "Структура HSE_VERSION_INFO | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- HSE_VERSION_INFO
dev_langs:
- C++
helpviewer_keywords:
- HSE_VERSION_INFO structure [MFC]
ms.assetid: 4837312d-68c8-4d05-9afa-1934d7d49b20
caps.latest.revision: 11
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 4a770b6508067913aec51b8b3878f33e30eed4bb
ms.openlocfilehash: 78b1ed79093db179e00f262b61934ff9c293ff18
ms.contentlocale: ru-ru
ms.lasthandoff: 10/09/2017

---
# <a name="hseversioninfo-structure"></a>Структура HSE_VERSION_INFO
Эта структура указывает `pVer` параметр в `CHttpServer::GetExtensionVersion` функции-члена. Он предоставляет номер версии ISA и текстовое описание ISA.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
typedef struct _HSE_VERSION_INFO {  
    DWORD dwExtensionVersion;  
    CHAR lpszExtensionDesc[HSE_MAX_EXT_DLL_NAME_LEN];  
} HSE_VERSION_INFO, *LPHSE_VERSION_INFO;  
```  
  
#### <a name="parameters"></a>Параметры  
 *dwExtensionVersion*  
 Номер версии ISA.  
  
 *lpszExtensionDesc*  
 Текстовое описание ISA. Реализация по умолчанию предоставляет замещающий текст; переопределить `CHttpServer::GetExtensionVersion` для предоставления собственное описание.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** httpext.h  
  
## <a name="see-also"></a>См. также  
 [Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)


