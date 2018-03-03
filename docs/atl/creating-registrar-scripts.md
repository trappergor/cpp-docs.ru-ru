---
title: "Создание сценариев для регистратор ATL | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- scripting, registry scripting
- ATL, registry
- registrar scripts [ATL]
- scripts, Registrar scripts
- scripts, creating
ms.assetid: cbd5024b-8061-4a71-be65-7fee90374a35
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b3bda4043693d14451a2de14cbc71fbecdcdddba
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="creating-registrar-scripts"></a>Creating Registrar Scripts
Сценарий регистратора доступ управляемых данными, а не управляемых API в системный реестр. Доступ на основе данных обычно более эффективны, так как он принимает только одну или две строки в сценарии, чтобы добавить раздел в реестр.  
  
 [Мастер элементов управления ATL](../atl/reference/atl-control-wizard.md) автоматически создает скрипт регистрации для COM-сервер. Этот скрипт можно найти в RGS-файл, связанный с данным объектом.  
  
 Обработчик скриптов регистратор ATL обрабатывает скрипта регистратора во время выполнения. ATL, автоматически вызывает обработчик скриптов во время установки сервера.  
  
 В этой статье рассматриваются следующие вопросы, связанные с скрипты регистратора:  
  
-   [Основные сведения о синтаксисе формы Бэкуса-Наура (BNF)](../atl/understanding-backus-nauer-form-bnf-syntax.md)  
  
-   [Основные сведения о деревьях синтаксического анализа](../atl/understanding-parse-trees.md)  
  
-   [Примеры скриптов реестра](../atl/registry-scripting-examples.md)  
  
-   [Использование подстановочных параметров (препроцессор регистратора)](../atl/using-replaceable-parameters-the-registrar-s-preprocessor.md)  
  
-   [Вызов скриптов](../atl/invoking-scripts.md)  
  
## <a name="see-also"></a>См. также  
 [Компонент реестра (регистратор)](../atl/atl-registry-component-registrar.md)

