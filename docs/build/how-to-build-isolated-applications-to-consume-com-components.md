---
title: "Как: построение изолированных приложений, использующих компоненты СОМ | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: isolated applications [C++]
ms.assetid: 04587547-1174-44ab-bd99-1292358fba20
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: aaeef56f122d10f983313ab1c839db40f4e92aa4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-build-isolated-applications-to-consume-com-components"></a>Практическое руководство. Построение изолированных приложений, использующих компоненты СОМ
Изолированные приложения представляют собой приложения, манифесты которых встроены в программу. Можно создать изолированных приложений, использующих компоненты СОМ.  
  
### <a name="to-add-com-references-to-manifests-of-isolated-applications"></a>Чтобы добавить COM-ссылок в манифесты изолированных приложений  
  
1.  Откройте страницы свойств проекта изолированного приложения.  
  
2.  Разверните **свойства конфигурации** узел, а затем разверните **инструмент манифеста** узла.  
  
3.  Выберите **изолированная модель COM** страницу свойств, а затем задайте **имя файла компонента** на имя COM-компонент, который будет в изолированном приложении.  
  
4.  Нажмите кнопку **ОК**.  
  
### <a name="to-build-manifests-into-isolated-applications"></a>Для создания манифестов в изолированные приложения  
  
1.  Откройте страницы свойств проекта изолированного приложения.  
  
2.  Разверните **свойства конфигурации** узел, а затем разверните **инструмент манифеста** узла.  
  
3.  Выберите **входной и выходной** страницу свойств, а затем задайте **внедренный манифест** значения свойства **Да**.  
  
4.  Нажмите кнопку **ОК**.  
  
5.  Постройте решение.  
  
## <a name="see-also"></a>См. также  
 [Изолированные приложения](http://msdn.microsoft.com/library/aa375190)   
 [О сборках Side-by-Side](http://msdn.microsoft.com/library/ff951640)