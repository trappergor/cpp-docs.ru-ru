---
title: "_acmdln, _tcmdln, _wcmdln | Документация Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _wcmdln
- _acmdln
apilocation:
- msvcrt.dll
apitype: DLLExport
f1_keywords:
- _acmdln
- acmdln
- _wcmdln
- wcmdln
- _tcmdln
- tcmdln
dev_langs:
- C++
helpviewer_keywords:
- _wcmdln global variable
- wcmdln global variable
- _acmdln global variable
- _tcmdln global variable
- tcmdln global variable
- acmdln global variable
ms.assetid: 4fc0a6a0-3f93-420a-a19f-5276061ba539
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: f2a5c42313699980828e663727dbc95039c23431
ms.contentlocale: ru-ru
ms.lasthandoff: 05/18/2017

---
# <a name="acmdln-tcmdln-wcmdln"></a>_acmdln, _tcmdln, _wcmdln
Внутренняя глобальная переменная CRT. Командная строка.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
char * _acmdln;  
wchar_t * _wcmdln;  
  
#ifdef WPRFLAG  
   #define _tcmdln _wcmdln  
#else  
   #define _tcmdln _acmdln  
```  
  
## <a name="remarks"></a>Примечания  
 Эти внутренние переменные CRT хранят полную командную строку. Они предоставляются в экспортируемых символах для CRT, но не предназначены для использования в коде. `_acmdln` хранит данные как строку символов. `_wcmdln` хранит данные как строку расширенных символов. `_tcmdln` может быть определена как `_acmdln` или`_wcmdln` в зависимости от обстоятельств.  
  
## <a name="see-also"></a>См. также  
 [Глобальные переменные](../c-runtime-library/global-variables.md)
