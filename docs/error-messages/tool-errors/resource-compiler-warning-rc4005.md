---
title: Предупреждение компилятора ресурсов RC4005 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- RC4005
dev_langs:
- C++
helpviewer_keywords:
- RC4005
ms.assetid: 71f03b4a-c9a9-415d-920f-bf2e58507f93
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 724764e443d4ab999c1df1247e9f5572ebdb2078
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33322488"
---
# <a name="resource-compiler-warning-rc4005"></a>Предупреждение компилятора ресурсов RC4005
«Идентификатор»: переопределение макросов  
  
 Идентификатор определен дважды. Компилятор использовал второе определение макроса.  
  
 Это предупреждение может быть вызвано определение макроса в командной строке и в коде с `#define` директивы. Она также может быть вызвана с импортом макроса из включаемых файлов.  
  
 Чтобы устранить предупреждение, удалите одно из определений или используйте `#undef` директиву перед вторым определением.