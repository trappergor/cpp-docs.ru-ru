---
title: 2.7 среда данных | Документация Майкрософт
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
ms.openlocfilehash: 17c60c621defa15c034f57d0af8f14637db54f03
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46378141"
---
# <a name="27-data-environment"></a>2.7 Среда данных

В этом разделе описываются директивы и несколько предложений для управления средой данных во время выполнения параллельных регионов следующим образом:

- Объект **threadprivate** директива (см. в следующем разделе) позволяет сделать области видимости файла, область пространства имен или переменные статические области видимости блока локального для потока.

- Предложения, которые могут быть указаны в директивы для управления доступом атрибуты переменных в течение конструкции параллельного или совместной работы описаны в [разделе 2.7.2](../../parallel/openmp/2-7-2-data-sharing-attribute-clauses.md) на стр. 25.