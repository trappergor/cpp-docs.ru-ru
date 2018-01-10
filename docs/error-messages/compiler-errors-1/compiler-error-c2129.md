---
title: "Ошибка компилятора C2129 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2129
dev_langs: C++
helpviewer_keywords: C2129
ms.assetid: 21a8223e-1d22-4baa-9ca1-922b7f751dd0
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3bad966f10fa63bc1ff6fdb6128e58ea9e8c5a37
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2129"></a>Ошибка компилятора C2129
Статическая функция «функция» объявлена, но не определена  
  
 При попытке отправить прямая ссылка `static` функция, которая не определена.  
  
 Объект `static` функция должна быть определена в области файла. Если функция определена в другом файле, он должен быть объявлен `extern`.