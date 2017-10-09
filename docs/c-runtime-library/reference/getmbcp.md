---
title: "_getmbcp | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _getmbcp
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-locale-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _getmbcp
- getmbcp
dev_langs:
- C++
helpviewer_keywords:
- code pages, determining current
- _getmbcp function
- getmbcp function
ms.assetid: 2db202d4-5c3d-4871-a0b8-ceb0b79ee7bb
caps.latest.revision: 13
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 16d1bf59dfd4b3ef5f037aed9c0f6febfdf1a2e8
ms.openlocfilehash: 4bc1000e9443d60e966ef6a929ed134acd44f1b7
ms.contentlocale: ru-ru
ms.lasthandoff: 10/09/2017

---
# <a name="getmbcp"></a>_getmbcp
Извлекает текущую кодовую страницу.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
int _getmbcp( void );  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращает текущую многобайтовую кодовую страницу. Возвращаемое значение 0 означает, что используется однобайтовая кодовая страница.  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`_getmbcp`|\<mbctype.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## <a name="see-also"></a>См. также  
 [_setmbcp](../../c-runtime-library/reference/setmbcp.md)
