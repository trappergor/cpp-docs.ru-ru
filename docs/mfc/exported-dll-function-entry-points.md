---
title: "Экспортировать точки входа DLL функция | Документы Microsoft"
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
- exporting DLLs [MFC], functions
- MFC, managing state data
- state management [MFC], exported DLLs
ms.assetid: 3268666e-d24b-44f2-80e8-7c80f73b93ca
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 28ded528d584e98b704b5f2d8e6e0a379a6a11a3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="exported-dll-function-entry-points"></a>Точки входа экспортированных функций DLL
Экспортированных функций DLL-библиотеки, используйте [AFX_MANAGE_STATE](reference/extension-dll-macros.md#afx_manage_state) макрос для поддержания соответствующего глобального состояния при переходе с DLL модуль DLL вызывающему приложению.  
  
 При вызове этот макрос задает `pModuleState`, указатель на `AFX_MODULE_STATE` структуру, содержащую глобальные данные этого модуля, состоянию действующие модуля в оставшейся области, содержащей функции. После закрывать область, содержащий макрос, предыдущее состояние действующие модуля автоматически восстановится.  
  
 Переключение это достигается путем создания экземпляра класса **AFX_MODULE_STATE** классов в стеке. В конструкторе, этот класс получает указатель на текущее состояние модуля и сохраняет его в переменной-члена и затем задает `pModuleState` как новое состояние действующие модуля. В его деструктор этот класс восстанавливает указателем, сохраненным в его переменной-члена как состояние действующие модуля.  
  
 При наличии экспортированную функцию, подобный диалоговое окно «» в библиотеке DLL, необходимо добавить следующий код в начало функции:  
  
 [!code-cpp[NVC_MFCConnectionPoints#6](../mfc/codesnippet/cpp/exported-dll-function-entry-points_1.cpp)]  
  
 Это меняет текущего состояния модуля с состоянием, возвращенные [AfxGetStaticModuleState](reference/extension-dll-macros.md#afxgetstaticmodulestate) до конца текущей области.  
  
 Проблемы с ресурсами в библиотеках DLL будет возникать, если `AFX_MANAGE_STATE` макрос не используется. По умолчанию MFC использует дескриптор ресурса основного приложения для загрузки шаблона ресурсов. Этот шаблон хранится в библиотеке DLL. Основной причиной является сведения о состоянии модуля MFC не была переключена с `AFX_MANAGE_STATE` макрос. Дескриптор ресурса будет восстановлена из состояния модуля MFC. Переключение состояния модуля не вызывает ресурсов неправильный дескриптор для использования.  
  
 `AFX_MANAGE_STATE`не нужно перевести в каждой функции в DLL. Например `InitInstance` может быть вызван кодом MFC в приложении без `AFX_MANAGE_STATE` поскольку MFC автоматически переключается в состояние модуля перед `InitInstance` и затем коммутаторы ее снова после `InitInstance` возвращает. То же самое верно для всех обработчиков на схеме сообщений. Обычные библиотеки DLL MFC фактически иметь специальное окно главную процедуру автоматического переключения состояния модуля перед отправкой сообщения.  
  
## <a name="see-also"></a>См. также  
 [Управление данными состояния модулей MFC](../mfc/managing-the-state-data-of-mfc-modules.md)

