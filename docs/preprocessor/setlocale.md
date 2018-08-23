---
title: setlocale | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- setlocale_CPP
- vc-pragma.setlocale
dev_langs:
- C++
helpviewer_keywords:
- pragmas, setlocale
- setlocale pragma
ms.assetid: e60b43d9-fbdf-4c4e-ac85-805523a13b86
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fa6ba2bec5c862bb336d4b9bea0f47aad91fe0c1
ms.sourcegitcommit: d4c803bd3a684d7951bf88dcecf1f14af43ae411
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/10/2018
ms.locfileid: "42540487"
---
# <a name="setlocale"></a>setlocale
Определяет языковой стандарт (страна или регион и язык), используемый при преобразовании констант и строковых литералов с расширенными символами.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
#pragma setlocale( "[locale-string]" )  
```  
  
## <a name="remarks"></a>Примечания  
 
Поскольку алгоритм преобразования многобайтовых символов в расширенные символы может зависеть от языкового стандарта или компиляция может выполняться в среде с языковым стандартом, отличным от стандарта среды, в которой будет запускаться исполняемый файл, данная директива #pragma позволяет указать целевой языковой стандарт во время компиляции. Это гарантирует, что строки с расширенными символами будут сохраняться в правильном формате.  
  
Значение по умолчанию *строке языкового стандарта* — «».  
  
Языковом стандарте «C» сопоставляет каждый символ в строке его значению с **wchar_t** (short без знака). Другие значения, допустимые для `setlocale` этих записей, которые находятся в [строки языка](../c-runtime-library/language-strings.md) списка. Например, можно указать директиву:  
  
```  
#pragma setlocale("dutch")  
```  
  
Возможность указания строки с названием языка зависит от кодовых страниц и идентификаторов языков, поддерживаемых компьютером.  
  
## <a name="see-also"></a>См. также  
 
[Директивы Pragma и ключевое слово __Pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)