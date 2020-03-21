---
title: Параметры, мастер страниц свойств ATL
ms.date: 05/09/2019
f1_keywords:
- vc.codewiz.class.atl.ppg.options
helpviewer_keywords:
- ATL Property Page Wizard, options
ms.assetid: a7107779-b2ea-4f99-b84b-7f3e0c504bc8
ms.openlocfilehash: a46a55cca221293e83a72bf0c2670e2343c744b0
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/21/2020
ms.locfileid: "80076216"
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
   |**Один**|Страница свойств выполняется только в первичном COM-потоке.|
   |**Подразделение**|Страница свойств может быть создана в любом подразделении с одним потоком. По умолчанию.|

- **Агрегирование**

   Добавляет поддержку агрегирования для страницы свойств, которую вы создаете. Подробные сведения см. в статье [Aggregation](../../atl/aggregation.md) (Агрегирование).

   |Параметр|Описание|
   |------------|-----------------|
   |**Да**|Создает страницу свойств, которую можно агрегировать.|
   |**Нет**|Создает страницу свойств, которую нельзя агрегировать.|
   |**Только**|Создает страницу свойств, экземпляр для которой можно создать только посредством агрегирования.|

::: moniker-end

## <a name="see-also"></a>См. также:

[Мастер страницы свойств ATL](../../atl/reference/atl-property-page-wizard.md)<br/>
[Строки, мастер страницы свойств ATL](../../atl/reference/strings-atl-property-page-wizard.md)
