---
title: Преимущества переносимости кодировки | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- character sets [C++], benefits
- portability [C++], character sets
ms.assetid: bd60b925-1498-4e4f-897b-4c8ce66edcf7
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4d1b78048baebfd89aed0ccc898c2bb9e3612525
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33853821"
---
# <a name="benefits-of-character-set-portability"></a>Преимущества переносимости кодировки
Можно обеспечить с помощью возможностей переносимости времени выполнения MFC и C, даже если не требуется делать в настоящее время интернационализировать приложение:  
  
-   Разработка переносимых приложений делает базу кода гибкие. Ее можно позже переместить легко Юникода и MBCS.  
  
-   Использование Юникода делает более эффективным приложений для Windows. Поскольку Windows используется Юникод, Юникод строк, передаваемых в и из операционной системы, необходимо преобразовывать, что снижает производительность.  

  
## <a name="see-also"></a>См. также  
 [Юникод и многобайтовая Кодировка](../text/unicode-and-mbcs.md)   
 [Поддержка Юникода](../text/support-for-unicode.md)