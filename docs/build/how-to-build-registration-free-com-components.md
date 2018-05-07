---
title: 'Как: сборки COM без регистрации компонентов | Документы Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- COM components, registration-free
ms.assetid: 7e585d6a-0314-45b2-8f1b-cae9ac4df037
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e54327344d61cc70e68b528c5f88f3d30f5d185a
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="how-to-build-registration-free-com-components"></a>Практическое руководство. Сборка не требующих регистрации компонентов COM
Без регистрации COM-компонентами являются компоненты COM, манифесты которых встроены в библиотеки DLL.  
  
### <a name="to-build-manifests-into-com-components"></a>Встраивание манифеста в компоненты COM  
  
1.  Откройте страницы свойств проекта для COM-компонента.  
  
2.  Разверните **свойства конфигурации** узел, а затем разверните **инструмент манифеста** узла.  
  
3.  Выберите **входной и выходной** страницу свойств, а затем задайте **внедренный манифест** значения свойства **Да**.  
  
4.  Нажмите кнопку **ОК**.  
  
5.  Постройте решение.  
  
## <a name="see-also"></a>См. также  
 [Изолированные приложения](http://msdn.microsoft.com/library/aa375190)   
 [О сборках Side-by-Side](http://msdn.microsoft.com/library/ff951640)   
 [Практическое руководство. Сборка изолированных приложений, использующих компоненты СОМ](../build/how-to-build-isolated-applications-to-consume-com-components.md)