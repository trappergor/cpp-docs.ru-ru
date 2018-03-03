---
title: "Списки инициализатора | Документы Microsoft"
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
- initializer lists
ms.assetid: b3e53442-9809-4105-9226-ae845bd20cae
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 1af020bec295f0f949b7ebb6abe88102f3942b1f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="initializer-lists"></a>Списки инициализатора
Списки инициализатора в конструкторах теперь вызываются перед конструктор базового класса.  
  
## <a name="remarks"></a>Примечания  
 До Visual C++ 2005 конструктор базового класса вызывался перед списком инициализатора при компиляции с помощью управляемых расширений для C++. Теперь при компиляции с параметром **/CLR**, сначала вызывается список инициализатора.  
  
## <a name="see-also"></a>См. также  
 [Общие изменения в языке (C++/CLI)](../dotnet/general-language-changes-cpp-cli.md)