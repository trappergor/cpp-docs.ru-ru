---
title: "ПРЕДПОЛОЖИМ | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: ASSUME
dev_langs: C++
helpviewer_keywords: ASSUME directive
ms.assetid: cd162070-aee9-4c65-babc-005c6cc73d7c
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 6046d19e628e75dee6e3f33b400c48dcbf317735
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="assume"></a>ASSUME
Включает проверку ошибок для значений регистра.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
ASSUME segregister:name [[, segregister:name]]...  
ASSUME dataregister:type [[, dataregister:type]]...  
ASSUME register:ERROR [[, register:ERROR]]...  
ASSUME [[register:]] NOTHING [[, register:NOTHING]]...  
```  
  
## <a name="remarks"></a>Примечания  
 После `ASSUME` вступили в силу, отслеживает изменения в значения, регистров, заданного код на языке ассемблера. **Ошибка** регистр используется приведет к ошибке. **Ничего не** удаляет зарегистрировать проверку ошибок. Можно сочетать различные виды допущения в одной инструкции.  
  
## <a name="see-also"></a>См. также  
 [Справочник по директивам](../../assembler/masm/directives-reference.md)