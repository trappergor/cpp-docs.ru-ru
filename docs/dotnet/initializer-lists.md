---
title: "Списки инициализатора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: initializer lists
ms.assetid: b3e53442-9809-4105-9226-ae845bd20cae
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 99d62f1aec8cf06fff5de98f4681ddc67c3a9e71
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="initializer-lists"></a>Списки инициализатора
Списки инициализатора в конструкторах теперь вызываются перед конструктор базового класса.  
  
## <a name="remarks"></a>Примечания  
 До Visual C++ 2005 конструктор базового класса вызывался перед списком инициализатора при компиляции с помощью управляемых расширений для C++. Теперь при компиляции с параметром **/CLR**, сначала вызывается список инициализатора.  
  
## <a name="see-also"></a>См. также  
 [Общие изменения в языке (C++/CLI)](../dotnet/general-language-changes-cpp-cli.md)