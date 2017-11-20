---
title: "Диапазоны чтения | Документация Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 99de29ce-ab14-46f4-97e1-2081fd996b53
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 96748c24fbf1e5adfebb72ba809533afeafebe38
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="reading-ranges"></a>Диапазоны чтения
**ANSI 4.9.6.2** Интерпретация символа дефиса (-), который не является ни первым, ни последним символом в списке сканирования для преобразования % [ в функции `fscanf`  
  
 В следующей строке  
  
```  
fscanf( fileptr, "%[A-Z]", strptr);  
```  
  
 считывается любое количество символов в диапазоне A–Z в строке, на которую указывает `strptr`.  
  
## <a name="see-also"></a>См. также  
 [Функции библиотеки](../c-language/library-functions.md)