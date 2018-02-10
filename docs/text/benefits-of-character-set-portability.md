---
title: "Преимущества переносимости кодировки | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- character sets [C++], benefits
- portability [C++], character sets
ms.assetid: bd60b925-1498-4e4f-897b-4c8ce66edcf7
caps.latest.revision: 
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7ce02fa834c39f629990d4f3c9785de94bd02196
ms.sourcegitcommit: a5916b48541f804a79891ff04e246628b5f9a24a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/09/2018
---
# <a name="benefits-of-character-set-portability"></a>Преимущества переносимости кодировки
Можно обеспечить с помощью возможностей переносимости времени выполнения MFC и C, даже если не требуется делать в настоящее время интернационализировать приложение:  
  
-   Разработка переносимых приложений делает базу кода гибкие. Ее можно позже переместить легко Юникода и MBCS.  
  
-   Использование Юникода делает более эффективным приложений для Windows. Поскольку Windows используется Юникод, Юникод строк, передаваемых в и из операционной системы, необходимо преобразовывать, что снижает производительность.  

  
## <a name="see-also"></a>См. также  
 [Юникод и многобайтовая Кодировка](../text/unicode-and-mbcs.md)   
 [Поддержка Юникода](../text/support-for-unicode.md)