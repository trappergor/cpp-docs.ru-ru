---
title: Параметры, мастер страниц свойств ATL
ms.date: 05/09/2019
f1_keywords:
- vc.codewiz.class.atl.ppg.options
helpviewer_keywords:
- ATL Property Page Wizard, options
ms.assetid: a7107779-b2ea-4f99-b84b-7f3e0c504bc8
ms.openlocfilehash: 74cf72feedd8dc8e1186d54a8abe840195964620
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2020
ms.locfileid: "92923662"
---
# <a name="options-atl-property-page-wizard"></a>Параметры, мастер страниц свойств ATL

::: moniker range="msvc-160"

Мастер страницы свойств в ATL недоступен в Visual Studio 2019 и более поздних версиях.

::: moniker-end

::: moniker range="<=msvc-150"

Эта страница мастера используется для определения потоковой модели и уровня агрегирования страницы свойств, которые вы создаете.

- **Модель потоков**

   Указывает потоковую модель, используемую на странице свойств.

   Подробные сведения см. в статье [Specifying the Threading Model for a Project (ATL)](../../atl/specifying-the-threading-model-for-a-project-atl.md) (Указание потоковой модели для проекта (ATL)).

   |Параметр|Описание|
   |------------|-----------------|
   |**Single**|Страница свойств выполняется только в первичном COM-потоке.|
   |**Разделение**|Страница свойств может быть создана в любом подразделении с одним потоком. Это значение используется по умолчанию.|

- **Статистической обработки**

   Добавляет поддержку агрегирования для страницы свойств, которую вы создаете. Подробные сведения см. в статье [Aggregation](../../atl/aggregation.md) (Агрегирование).

   |Параметр|Описание|
   |------------|-----------------|
   |**Да**|Создает страницу свойств, которую можно агрегировать.|
   |**Нет**|Создает страницу свойств, которую нельзя агрегировать.|
   |**Только**|Создает страницу свойств, экземпляр для которой можно создать только посредством агрегирования.|

::: moniker-end

## <a name="see-also"></a>См. также статью

[Мастер страницы свойств ATL](../../atl/reference/atl-property-page-wizard.md)<br/>
[Строки, мастер страниц свойств ATL](../../atl/reference/strings-atl-property-page-wizard.md)
