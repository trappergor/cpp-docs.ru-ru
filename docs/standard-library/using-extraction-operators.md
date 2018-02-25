---
title: "Использование операторов извлечения | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- extraction operators [C++]
- '&gt;&gt; operator [C++], extraction operators'
- operators [C++], extraction
ms.assetid: a961e1a9-4897-41de-b210-89d5b2d051ae
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: bb9e62ffd1e466fd220012717e278b79bbce3e1f
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
---
# <a name="using-extraction-operators"></a>Использование операторов извлечения
Оператор извлечения (`>>`), который предварительно определен для всех стандартных типов данных C++, позволяет проще всего получить байты из объекта входного потока.  
  
 Операторы извлечения форматированного текста используют пробел в качестве разделителя значений входных данных. Это неудобно, если текстовое поле содержит несколько слов или цифры, разделенные запятыми. В этом случае одним из альтернативных вариантов является считывание блока текста с пробелами с помощью функции-члена для обработки неформатированного ввода [istream::getline](../standard-library/basic-istream-class.md#getline) и последующий разбор блока с помощью специальных функций. Другой способ — наследовать класс входного потока с помощью функции-члена, например `GetNextToken`, которая может вызывать члены istream для извлечения и форматирования символьных данных.  
  
## <a name="see-also"></a>См. также  
 [Потоки ввода](../standard-library/input-streams.md)

