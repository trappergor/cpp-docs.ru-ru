---
title: 2.7 среда данных | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 74e44b3c-e18c-4773-8e78-cd6c4413ae57
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d1b0f253ce14ffc5d3740e582a9a51feea56ad32
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
---
# <a name="27-data-environment"></a>2.7 Среда данных
В этом разделе описываются директивы и несколько предложений для контроля среды данных во время выполнения параллельных регионов, следующим образом:  
  
-   Объект **threadprivate** директивы (см. следующий раздел) позволяет сделать области видимости файла, область пространства имен или переменных статических области видимости блока локальной для потока.  
  
-   Предложения, которые могут быть указаны для директив для управления доступом атрибуты переменных в течение конструкции параллельный или совместной работы описаны в [раздел 2.7.2](../../parallel/openmp/2-7-2-data-sharing-attribute-clauses.md) на странице 25.