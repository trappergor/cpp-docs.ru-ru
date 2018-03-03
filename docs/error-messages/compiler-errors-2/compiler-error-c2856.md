---
title: "Ошибка компилятора C2856 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2856
dev_langs:
- C++
helpviewer_keywords:
- C2856
ms.assetid: fe616c51-124e-49e3-9dd8-883ec1660680
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ab5fdd09fbbd7c6b1f213404dfbf6d9d9e5612ea
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2856"></a>Ошибка компилятора C2856
\#Директива #pragma hdrstop не может находиться внутри блока #if  
  
 `hdrstop` Нельзя помещать внутрь блока условной компиляции.  
  
 Переместить `#pragma hdrstop` область, которая не содержится в инструкции `#if/#endif` блока.