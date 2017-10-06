---
title: "Последовательности символов | Документация Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: 1e6961a9-150e-4c13-b427-9af4b6a1fb7a
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: 67ddf6a6712e0c98ea7b7866b3267d56308a5b5c
ms.contentlocale: ru-ru
ms.lasthandoff: 05/18/2017

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
