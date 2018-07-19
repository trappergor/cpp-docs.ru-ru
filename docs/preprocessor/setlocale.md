---
title: setlocale | Документы Microsoft
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
ms.openlocfilehash: 0cfabfa3c83fe2ff90a6f7dbe07d5205f7a6f9a9
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
ms.locfileid: "33847420"
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