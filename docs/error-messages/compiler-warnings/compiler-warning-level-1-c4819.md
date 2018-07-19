---
title: Ошибка компилятора предупреждение (уровень 1) C4819 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4819
dev_langs:
- C++
helpviewer_keywords:
- C4819
ms.assetid: c0316e85-249c-414d-9df0-622d077c6bc2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 718e0783c3f7afcc9af958f7940f437ac4c944b7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33283384"
---
# <a name="compiler-warning-level-1-c4819"></a>Предупреждение компилятора (уровень 1) C4819
Файл содержит символ, который нельзя отобразить с помощью текущей кодовой страницы (номер). Сохраните файл в формате Юникода, чтобы избежать потери данных.  
  
 Ошибка C4819 возникает, когда файл исходного кода ANSI компилируется в системе, кодовая страница которой не может отобразить все символы файла.  
  
 Чтобы устранить ошибку C4819, сохраните файл в формате Юникода. В Visual Studio выберите **файл**, **Дополнительные параметры сохранения**. В **Дополнительные параметры сохранения** диалогового окна выберите кодировку, которая может представлять все символы в файле — UTF-8 и нажмите кнопку **ОК**.