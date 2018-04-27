---
title: Проверка на наличие ошибок извлечения | Документы Майкрософт
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
- extraction errors
ms.assetid: 6a681028-adba-4557-8f7b-f137932905f8
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9394f387546f9b9dccf72f532148aa2b9161ce15
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="testing-for-extraction-errors"></a>Проверка на наличие ошибок извлечения

Функции обработки ошибок вывода, рассматриваемые в разделе [Функции обработки ошибок](../standard-library/output-file-stream-member-functions.md), применяются к входным потокам. Проверка на наличие ошибок во время извлечения очень важна. Представьте себе следующую ситуацию:

```cpp
cin>> n;
```

Если `n` — это целое число со знаком, значение больше 32 767 (максимальное допустимое значение или MAX_INT) задает бит `fail` потока, а объект `cin` становится непригодным для использования. Все последующие извлечения приводят к немедленному возврату без сохранения значений.

## <a name="see-also"></a>См. также

[Входные потоки](../standard-library/input-streams.md)<br/>
