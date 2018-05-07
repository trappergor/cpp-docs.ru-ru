---
title: Ошибка компилятора C2856 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2856
dev_langs:
- C++
helpviewer_keywords:
- C2856
ms.assetid: fe616c51-124e-49e3-9dd8-883ec1660680
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ac67538a10d39bc68059b0a7d1aaf73a381abb2a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2856"></a>Ошибка компилятора C2856
\#Директива #pragma hdrstop не может находиться внутри блока #if  
  
 `hdrstop` Нельзя помещать внутрь блока условной компиляции.  
  
 Переместить `#pragma hdrstop` область, которая не содержится в инструкции `#if/#endif` блока.