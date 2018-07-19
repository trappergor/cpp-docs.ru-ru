---
title: Проверка на наличие ошибок извлечения | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- extraction errors
ms.assetid: 6a681028-adba-4557-8f7b-f137932905f8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dc84277b654a79eebd38461c3ee83aefd533e4a8
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33853902"
---
# <a name="testing-for-extraction-errors"></a>Проверка на наличие ошибок извлечения

Функции обработки ошибок вывода, рассматриваемые в разделе [Функции обработки ошибок](../standard-library/output-file-stream-member-functions.md), применяются к входным потокам. Проверка на наличие ошибок во время извлечения очень важна. Представьте себе следующую ситуацию:

```cpp
cin>> n;
```

Если `n` — это целое число со знаком, значение больше 32 767 (максимальное допустимое значение или MAX_INT) задает бит `fail` потока, а объект `cin` становится непригодным для использования. Все последующие извлечения приводят к немедленному возврату без сохранения значений.

## <a name="see-also"></a>См. также

[Входные потоки](../standard-library/input-streams.md)<br/>
