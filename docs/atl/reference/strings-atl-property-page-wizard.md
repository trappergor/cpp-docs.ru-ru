---
title: Строки, мастер страницы свойств ATL
ms.date: 05/09/2019
f1_keywords:
- vc.codewiz.class.atl.ppg.strings
helpviewer_keywords:
- ATL Property Page Wizard, strings
ms.assetid: 00547db6-911f-49eb-92e1-2ba67079d4df
ms.openlocfilehash: 04178c435bbd0ca80e412efc39a1b736062d95e7
ms.sourcegitcommit: fc1de63a39f7fcbfe2234e3f372b5e1c6a286087
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2019
ms.locfileid: "65706765"
---
# <a name="strings-atl-property-page-wizard"></a>Строки, мастер страницы свойств ATL

::: moniker range="vs-2019"

Мастер страницы свойств в ATL недоступен в Visual Studio 2019 и более поздних версиях.

::: moniker-end

::: moniker range="<=vs-2017"

Предоставляет текст, связанный со страницей свойств.

- **Заголовок**

   Задает текст, отображаемый для вкладки на странице свойств.

- **Строка документа**

   Задает текстовую строку, описывающую страницу. Эта строка может отображаться в диалоговом окне страницы свойств. Фрейм свойства может использовать описание в строке состояния или в подсказке. Стандартный фрейм свойства в настоящее время не использует эту строку.

- **Файл справки**

   Задает имя файла справки, в котором описывается использование страницы свойств. Это имя не должно содержать путь. Когда пользователь нажимает кнопку **Справка**, фрейм открывает файл справки в каталоге, указанном в значении ключа HelpDir в записях реестра страницы свойств в разделе идентификатора CLSID.

::: moniker-end

## <a name="see-also"></a>См. также

[Мастер страницы свойств ATL](../../atl/reference/atl-property-page-wizard.md)<br/>
[Параметры, мастер страниц свойств ATL](../../atl/reference/options-atl-property-page-wizard.md)
