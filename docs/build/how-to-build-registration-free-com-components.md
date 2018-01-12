---
title: "Как: сборки COM без регистрации компонентов | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: COM components, registration-free
ms.assetid: 7e585d6a-0314-45b2-8f1b-cae9ac4df037
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 018a3ba707f4c5cff73b5a5c54f82400a79a8d46
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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