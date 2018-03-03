---
title: "2.7 среда данных | Документы Microsoft"
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
ms.assetid: 74e44b3c-e18c-4773-8e78-cd6c4413ae57
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e018a2c1b20bef640852ced913dc90266e733c06
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="27-data-environment"></a>2.7 Среда данных
В этом разделе описываются директивы и несколько предложений для контроля среды данных во время выполнения параллельных регионов, следующим образом:  
  
-   Объект **threadprivate** директивы (см. следующий раздел) позволяет сделать области видимости файла, область пространства имен или переменных статических области видимости блока локальной для потока.  
  
-   Предложения, которые могут быть указаны для директив для управления доступом атрибуты переменных в течение конструкции параллельный или совместной работы описаны в [раздел 2.7.2](../../parallel/openmp/2-7-2-data-sharing-attribute-clauses.md) на странице 25.