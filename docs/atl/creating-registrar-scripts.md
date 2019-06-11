---
title: Создание скриптов для регистратора ATL
ms.date: 05/14/2014
helpviewer_keywords:
- scripting, registry scripting
- ATL, registry
- registrar scripts [ATL]
- scripts, Registrar scripts
- scripts, creating
ms.assetid: cbd5024b-8061-4a71-be65-7fee90374a35
ms.openlocfilehash: f32606701ea08736985f0b0dd2ed82712040a049
ms.sourcegitcommit: fc1de63a39f7fcbfe2234e3f372b5e1c6a286087
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2019
ms.locfileid: "65707057"
---
# <a name="creating-registrar-scripts"></a>Создание скриптов регистратора

Скрипт регистратора обеспечивает доступ к реестру системы на основе данных, а не на основе API. Основанный на данных подход, как правило, более эффективен, поскольку для добавления раздела в реестр достаточно включить в скрипту одну или две строки.

[Мастер элементов управления ATL](../atl/reference/atl-control-wizard.md) автоматически создает скрипт регистратора для COM-сервера. Этот скрипт находится в RGS-файле, связанном с вашим объектом.

Во время выполнения обработку скрипта регистратора осуществляет обработчик скриптов регистратора ATL. ATL автоматически вызывает обработчик скриптов в процессе установки сервера.

В этой статье рассматриваются следующие вопросы, связанные со скриптами регистратора.

- [Основные сведения о синтаксисе формы Бэкуса-Наура (BNF)](../atl/understanding-backus-naur-form-bnf-syntax.md)

- [Основные сведения о деревьях синтаксического анализа](../atl/understanding-parse-trees.md)

- [Примеры скриптов реестра](../atl/registry-scripting-examples.md)

- [Использование подстановочных параметров (препроцессор регистратора)](../atl/using-replaceable-parameters-the-registrar-s-preprocessor.md)

- [Вызов скриптов](../atl/invoking-scripts.md)

## <a name="see-also"></a>См. также

[Компонент реестра (регистратор)](../atl/atl-registry-component-registrar.md)
