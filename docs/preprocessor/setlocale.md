---
title: "setlocale | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c52697fffb27e6fd25936f3c6566f027cc265c18
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
---
# <a name="setlocale"></a>setlocale
Определяет языковой стандарт (страна или регион и язык), используемый при преобразовании констант и строковых литералов с расширенными символами.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
#pragma setlocale( "[locale-string]" )  
```  
  
## <a name="remarks"></a>Примечания  
 Поскольку алгоритм преобразования многобайтовых символов в расширенные символы может зависеть от языкового стандарта или компиляция может выполняться в среде с языковым стандартом, отличным от стандарта среды, в которой будет запускаться исполняемый файл, данная директива #pragma позволяет указать целевой языковой стандарт во время компиляции. Это гарантирует, что строки с расширенными символами будут сохраняться в правильном формате.  
  
 Значение по умолчанию *строка языковых стандартов* является «».  
  
 Языковой стандарт "C" сопоставляет каждый символ в строке его значению с типом `wchar_t` (unsigned short). Другие значения, которые являются допустимыми для `setlocale` являются те операции, которые находятся в [строки языка](../c-runtime-library/language-strings.md) списка. Например, можно указать директиву:  
  
```  
#pragma setlocale("dutch")  
```  
  
 Возможность указания строки с названием языка зависит от кодовых страниц и идентификаторов языков, поддерживаемых компьютером.  
  
## <a name="see-also"></a>См. также  
 [Директивы Pragma и ключевое слово __Pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)