---
title: Структура HSE_VERSION_INFO | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- HSE_VERSION_INFO
dev_langs:
- C++
helpviewer_keywords:
- HSE_VERSION_INFO structure [MFC]
ms.assetid: 4837312d-68c8-4d05-9afa-1934d7d49b20
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: acdf63e062aab1407daee461e22f00f5d3c59cee
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
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

