---
title: "Неустранимая ошибка C1005 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C1005
dev_langs:
- C++
helpviewer_keywords:
- C1005
ms.assetid: 150daf8e-a38a-4669-9c1a-a05b5a1f65ef
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 44040416fe94c2117938aa70c9e241cb5cd832fb
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="fatal-error-c1005"></a>Неустранимая ошибка C1005
слишком большая строка для буфера  
  
 Строка в промежуточном файле компилятора вызвала переполнение буфера.  
  
 Эта ошибка может возникнуть, если размер параметра, передаваемого в параметр компилятора [/Fd](../../build/reference/fd-program-database-file-name.md) или [/Yl](../../build/reference/yl-inject-pch-reference-for-debug-library.md) , превышает 256 байт.