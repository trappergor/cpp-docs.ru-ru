---
title: 'Практическое: построение без регистрации COM-компонентов | Документация Майкрософт'
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
ms.openlocfilehash: 1eaf9417f4d2b3b825933589556055772b84e057
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43197417"
---
# <a name="how-to-build-registration-free-com-components"></a>Практическое руководство. Сборка не требующих регистрации компонентов COM
Без регистрации COM-компонентами являются компоненты COM, содержащие манифесты, встроенные в библиотеки DLL.  
  
### <a name="to-build-manifests-into-com-components"></a>Для создания манифестов в COM-компонентов  
  
1.  Откройте страницы свойств проекта для COM-компонента.  
  
2.  Разверните **свойства конфигурации** узел, а затем разверните **инструмент манифеста** узла.  
  
3.  Выберите **входные и выходные данные** страницу свойств, а затем задайте **внедренный манифест** равным **Да**.  
  
4.  Нажмите кнопку **ОК**.  
  
5.  Постройте решение.  
  
## <a name="see-also"></a>См. также  
 [Изолированные приложения](/windows/desktop/SbsCs/isolated-applications)   
 [О сборках Side-by-Side](/windows/desktop/SbsCs/about-side-by-side-assemblies-)   
 [Практическое руководство. Сборка изолированных приложений, использующих компоненты СОМ](../build/how-to-build-isolated-applications-to-consume-com-components.md)