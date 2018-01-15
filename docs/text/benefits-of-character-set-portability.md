---
title: "Преимущества переносимости кодировки | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- character sets [C++], benefits
- portability [C++], character sets
ms.assetid: bd60b925-1498-4e4f-897b-4c8ce66edcf7
caps.latest.revision: "8"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 554137352c0a8f7275a051e4026020fce25edbb8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="benefits-of-character-set-portability"></a>Преимущества переносимости кодировки
Можно обеспечить с помощью возможностей переносимости времени выполнения MFC и C, даже если не требуется делать в настоящее время интернационализировать приложение:  
  
-   Разработка переносимых приложений делает базу кода гибкие. Ее можно позже переместить легко Юникода и MBCS.  
  
-   Использование Юникода делает приложения для Windows 2000, более эффективным. Поскольку Windows 2000 использует Юникод, строки не в Юникоде, передаваемые в и из операционной системы должны быть переведены, что снижает производительность.  
  
-   С помощью MBCS позволяет обеспечить поддержку международных рынков для платформ Win32, отличных от Windows 2000, такие как Windows 95 или Windows 98.  
  
## <a name="see-also"></a>См. также  
 [Юникод и многобайтовая Кодировка](../text/unicode-and-mbcs.md)   
 [Поддержка Юникода](../text/support-for-unicode.md)