---
title: "___lc_codepage_func | Документация Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: ___lc_codepage_func
apilocation:
- msvcr120.dll
- msvcr110_clr0400.dll
- msvcr80.dll
- msvcr100.dll
- msvcr90.dll
- msvcr110.dll
- msvcrt.dll
apitype: DLLExport
f1_keywords:
- lc_codepage_func
- ___lc_codepage_func
dev_langs: C++
helpviewer_keywords: ___lc_codepage_func
ms.assetid: 6a663bd0-5a63-4a2f-9507-872ec1582aae
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 0d73f285647d3ef4947454fd4bc831b746ef754c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="lccodepagefunc"></a>___lc_codepage_func
Внутренняя функция CRT. Получает текущую кодовую страницу потока.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
UINT ___lc_codepage_func(void);  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Текущая кодовая страница потока.  
  
## <a name="remarks"></a>Примечания  
 `___lc_codepage_func` — это внутренняя функция CRT, которая используется другими функциями CRT для получения текущей кодовой страницы из локального хранилища потока для данных CRT. Эти сведения также доступны при использовании функции [_get_current_locale](../c-runtime-library/reference/get-current-locale.md).  
  
 *Кодовая страница* представляет собой сопоставление однобайтовых или двухбайтовых кодов с конкретными символами. Разные кодовые страницы включают разные специальные символы, как правило, настроенные для языка или группы языков. Дополнительные сведения о кодовых страницах см. в разделе [Code Pages](../c-runtime-library/code-pages.md).  
  
 Внутренние функции CRT связаны с конкретной реализацией и подлежат изменению в каждом выпуске. Мы не рекомендуем использовать их в коде.  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`___lc_codepage_func`|crt\src\setlocal.h|  
  
## <a name="see-also"></a>См. также  
 [_get_current_locale](../c-runtime-library/reference/get-current-locale.md)   
 [setlocale, _wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)   
 [_create_locale, _wcreate_locale](../c-runtime-library/reference/create-locale-wcreate-locale.md)   
 [_free_locale](../c-runtime-library/reference/free-locale.md)