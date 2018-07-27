---
title: Последовательности символов | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: 1e6961a9-150e-4c13-b427-9af4b6a1fb7a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 85cf817a4d50346b9d10a9a9d1bc27abb5904433
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32382394"
---
# <a name="character-sequences"></a>Последовательности символов
**ANSI 3.8.2** Сопоставление последовательностей символов в исходных файлах  
  
 В операторах препроцессора используется тот же набор символов, что и в операторах исходного файла, однако escape-последовательности не поддерживаются.  
  
 Таким образом, при определении пути к включаемому файлу необходимо указывать только одну обратную косую черту.  
  
```  
#include "path1\path2\myfile"  
```  
  
 Однако в самом исходном коде необходимо указывать две обратные косые черты подряд:  
  
```  
fil = fopen( "path1\\path2\\myfile", "rt" );  
```  
  
## <a name="see-also"></a>См. также  
 [Директивы предварительной обработки](../c-language/preprocessing-directives.md)