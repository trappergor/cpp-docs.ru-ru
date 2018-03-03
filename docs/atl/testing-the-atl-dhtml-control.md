---
title: "Тестирование элемента управления ATL DHTML | Документы Microsoft"
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
- HTML controls, testing
- testing controls
- DHTML controls
- DHTML controls, testing
ms.assetid: 0e4b4358-80ce-4505-8b06-ef4f30b1d1f0
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: dd92900ffbb8170e942053910d3faedd1f5ab2ed
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="testing-the-atl-dhtml-control"></a>Тестирование элемента управления ATL DHTML
После создания проекта можно создать и протестировать пример элемента управления. Перед этим следует используйте представления классов и обозревателя решений для проверки проекта. Элементы проекта описаны более подробно в [определения элементов управления DHTML проекта](../atl/identifying-the-elements-of-the-dhtml-control-project.md).  
  
#### <a name="to-build-and-test-the-atl-dhtml-control"></a>Построение и тестирование элемента управления ATL DHTML  
  
1.  Выполните построение проекта. Из **построения** меню, нажмите кнопку **построить решение**.  
  
2.  После завершения построения, откройте тестовый контейнер. В разделе [тестирование свойств и событий с использованием тестового контейнера](../mfc/testing-properties-and-events-with-test-container.md) сведения о том, как получить доступ к контейнеру теста.  
  
3.  В тестовом контейнере из **изменить** меню, нажмите кнопку **вставить новый элемент управления**.  
  
4.  В **вставить элемент** диалогового окна выберите элемент управления из списка. Помните, что его имя основано на короткое имя, которое указано в мастер элементов управления ATL. Нажмите кнопку **ОК**.  
  
5.  Проверьте элемент управления. Обратите внимание, что он имеет полосы прокрутки. Используйте элемент управления обрабатывает размер элемента управления, чтобы активировать полосы прокрутки.  
  
6.  Тестирование элемента управления кнопки. Изменения цвета фона, цвета, на кнопке.  
  
7.  Закройте тестовый контейнер.  
  
 После этого повторите [изменения элемента управления DHTML](../atl/modifying-the-atl-dhtml-control.md).  
  
## <a name="see-also"></a>См. также  
 [Поддержка элементов управления DHTML](../atl/atl-support-for-dhtml-controls.md)

