---
title: 2.4.3 единый конструкция | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 15c180cd-e462-4b41-bf8c-cb8b1afb1a9b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 81abf5324c215b9011ecbd774626a213c2eda653
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46376504"
---
# <a name="243-single-construct"></a>2.4.3 Конструкция single

**Единый** директива определяет конструкцию, которая указывает, что связанный структурированном блоке выполняется только одним потоком в группе (не обязательно главный поток). Синтаксис **единый** директива выглядит следующим образом:

```
#pragma omp single [clause[[,] clause] ...] new-linestructured-block
```

Предложение является одним из следующих:

**закрытый (** *списка переменной* **)**

**firstprivate (** *списка переменной* **)**

**copyprivate (** *списка переменной* **)**

**nowait**

Есть неявное барьера после **единый** создать, если не **nowait** указано предложение.

Ограничения для **единый** директива таковы:

- Только один **nowait** предложения могут отображаться на **единый** директива.

- **Copyprivate** предложение не должны использоваться с **nowait** предложение.

## <a name="cross-references"></a>Перекрестные ссылки:

- **закрытый**, **firstprivate**, и **copyprivate** предложений, см. в разделе [разделе 2.7.2](../../parallel/openmp/2-7-2-data-sharing-attribute-clauses.md) на стр. 25.