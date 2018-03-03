---
title: "Ошибка компилятора предупреждение (уровень 1) C4819 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4819
dev_langs:
- C++
helpviewer_keywords:
- C4819
ms.assetid: c0316e85-249c-414d-9df0-622d077c6bc2
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b515a3f5e840bbc93f37420866023ee778b404ee
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4819"></a>Предупреждение компилятора (уровень 1) C4819
Файл содержит символ, который нельзя отобразить с помощью текущей кодовой страницы (номер). Сохраните файл в формате Юникода, чтобы избежать потери данных.  
  
 Ошибка C4819 возникает, когда файл исходного кода ANSI компилируется в системе, кодовая страница которой не может отобразить все символы файла.  
  
 Чтобы устранить ошибку C4819, сохраните файл в формате Юникода. В Visual Studio выберите **файл**, **Дополнительные параметры сохранения**. В **Дополнительные параметры сохранения** диалогового окна выберите кодировку, которая может представлять все символы в файле — UTF-8 и нажмите кнопку **ОК**.