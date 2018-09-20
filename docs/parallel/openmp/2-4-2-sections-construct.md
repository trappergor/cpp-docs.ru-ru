---
title: 2.4.2 конструкция sections | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: e9e6e3ea-7fc9-4925-8f68-92b8a5bb1e76
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 35ae940e37b40cbb9c883c4d7d6bca7b0fa65520
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46410552"
---
# <a name="242-sections-construct"></a>2.4.2 Конструкция sections

**Разделах** директива идентифицирует noniterative конструкции совместной работы, указывающий набор конструкций, которые будет разделен между потоками в группе. В каждом разделе выполняется один раз потоком в группе. Синтаксис **разделах** директива выглядит следующим образом:

```
#pragma omp sections [clause[[,] clause] ...] new-line
   {
   [#pragma omp section new-line]
      structured-block
   [#pragma omp section new-linestructured-block ]
...
}
```

Предложение является одним из следующих:

**закрытый (** *списка переменной* **)**

**firstprivate (** *списка переменной* **)**

**lastprivate (** *списка переменной* **)**

**сокращение (** *оператор* **:***списка переменной* **)** 

**nowait**

В каждом разделе предшествует **разделе** директивы, несмотря на то что **разделе** директива не является обязательным для первого раздела. **Разделе** директивы необходимо заключать в лексическую область **разделах** директива. Есть неявное барьер в конце **разделах** создать, если не **nowait** указан.

Ограничения для **разделах** директива таковы:

- Объект **разделе** директива не должна находиться за пределами лексическую область **разделах** директива.

- Только один **nowait** предложения могут отображаться на **разделах** директива.

## <a name="cross-references"></a>Перекрестные ссылки:

- **закрытый**, **firstprivate**, **lastprivate**, и **сокращения** предложений, см. в разделе [разделе 2.7.2](../../parallel/openmp/2-7-2-data-sharing-attribute-clauses.md) на стр. 25.