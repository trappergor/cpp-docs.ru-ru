---
title: 2.4.3 Конструкция single
ms.date: 11/04/2016
ms.assetid: 15c180cd-e462-4b41-bf8c-cb8b1afb1a9b
ms.openlocfilehash: 7dda98ee83ee08adc29830a9c4ada71a208705fe
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50466369"
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