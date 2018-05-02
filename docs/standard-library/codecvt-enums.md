---
title: Перечисления &lt;codecvt&gt; | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- codecvt/std::codecvt_mode
ms.assetid: 46a8b073-01bc-46d3-b3d3-a8540f9422c1
helpviewer_keywords:
- std::codecvt_mode
caps.latest.revision: 10
manager: ghogen
ms.openlocfilehash: 8ab60ab806afa89cfe22cd429eff59fefb806c34
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="ltcodecvtgt-enums"></a>Перечисления &lt;codecvt&gt;

## <a name="codecvt_mode"></a> Перечисление codecvt_mode

Задает сведения о конфигурации для аспектов [языкового стандарта](../standard-library/locale-class.md).

```cpp
enum codecvt_mode {
    consume_header = 4,
    generate_header = 2,
    little_endian = 1
 };
```

### <a name="remarks"></a>Примечания

Перечисление определяет три константы, которые поставляют сведения о конфигурации для аспектов языкового стандарта, объявленных в [\<codecvt>](../standard-library/codecvt.md). Это могут быть следующие значения:

- `consume_header`, чтобы использовать начальную последовательность заголовка при чтении многобайтовой последовательности и определении порядка байтов следующей многобайтовой последовательности для чтения;

- `generate_header`, чтобы создавать начальную последовательность заголовка при записи многобайтовой последовательности для объявления порядка байтов следующей многобайтовой последовательности для записи;

- `little_endian`, чтобы создавать многобайтовую последовательность в прямом порядке байтов, в отличие от порядка "сначала старший байт" по умолчанию.

Эти константы можно связывать логическим оператором OR в произвольные сочетания.

## <a name="see-also"></a>См. также

[\<codecvt>](../standard-library/codecvt.md)<br/>
