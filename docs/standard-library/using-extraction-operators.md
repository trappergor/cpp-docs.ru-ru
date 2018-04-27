---
title: Использование операторов извлечения | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- extraction operators [C++]
- '&gt;&gt; operator [C++], extraction operators'
- operators [C++], extraction
ms.assetid: a961e1a9-4897-41de-b210-89d5b2d051ae
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 26dec4b3bdad481e53e88ca2c91c82161de9bf81
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="using-extraction-operators"></a>Использование операторов извлечения

Оператор извлечения (`>>`), который предварительно определен для всех стандартных типов данных C++, позволяет проще всего получить байты из объекта входного потока.

Операторы извлечения форматированного текста используют пробел в качестве разделителя значений входных данных. Это неудобно, если текстовое поле содержит несколько слов или цифры, разделенные запятыми. В этом случае одним из альтернативных вариантов является считывание блока текста с пробелами с помощью функции-члена для обработки неформатированного ввода [istream::getline](../standard-library/basic-istream-class.md#getline) и последующий разбор блока с помощью специальных функций. Другой способ — наследовать класс входного потока с помощью функции-члена, например `GetNextToken`, которая может вызывать члены istream для извлечения и форматирования символьных данных.

## <a name="see-also"></a>См. также

[Входные потоки](../standard-library/input-streams.md)<br/>
