---
title: Параметры, мастер страниц свойств ATL
ms.date: 05/09/2019
f1_keywords:
- vc.codewiz.class.atl.ppg.options
helpviewer_keywords:
- ATL Property Page Wizard, options
ms.assetid: a7107779-b2ea-4f99-b84b-7f3e0c504bc8
ms.openlocfilehash: 205f6d3debafe22373355af12ef88c83d6a01911
ms.sourcegitcommit: fc1de63a39f7fcbfe2234e3f372b5e1c6a286087
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2019
ms.locfileid: "65707006"
---
# <a name="options-atl-property-page-wizard"></a>Параметры, мастер страниц свойств ATL


::: moniker range="vs-2019"

Мастер страницы свойств в ATL недоступен в Visual Studio 2019 и более поздних версиях.

::: moniker-end

::: moniker range="<=vs-2017"

Эта страница мастера используется для определения потоковой модели и уровня агрегирования страницы свойств, которые вы создаете.

- **Потоковая модель**

   Указывает потоковую модель, используемую на странице свойств.

   Подробные сведения см. в статье [Specifying the Threading Model for a Project (ATL)](../../atl/specifying-the-threading-model-for-a-project-atl.md) (Указание потоковой модели для проекта (ATL)).

   |Параметр|Описание|
   |------------|-----------------|
   |**Single**|Страница свойств выполняется только в первичном COM-потоке.|
   |**Подразделение**|Страница свойств может быть создана в любом подразделении с одним потоком. По умолчанию.|

- **Статистическая обработка**

   Добавляет поддержку агрегирования для страницы свойств, которую вы создаете. Подробные сведения см. в статье [Aggregation](../../atl/aggregation.md) (Агрегирование).

   |Параметр|Описание|
   |------------|-----------------|
   |**Да**|Создает страницу свойств, которую можно агрегировать.|
   |**No**|Создает страницу свойств, которую нельзя агрегировать.|
   |**Только**|Создает страницу свойств, экземпляр для которой можно создать только посредством агрегирования.|

::: moniker-end

## <a name="see-also"></a>См. также

[Мастер страницы свойств ATL](../../atl/reference/atl-property-page-wizard.md)<br/>
[Строки, мастер страницы свойств ATL](../../atl/reference/strings-atl-property-page-wizard.md)
