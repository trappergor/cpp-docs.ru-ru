---
title: "Инициализация ядра базы данных DAO и прекращение работы | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.macros.data
dev_langs:
- C++
helpviewer_keywords:
- DAO (Data Access Objects), termination
- DAO (Data Access Objects), initialization
ms.assetid: a7edf31c-e7c2-4f3e-aada-63c3e48781da
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 32dbcb02615f552a2bb26ec047b0b817bb828a95
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="dao-database-engine-initialization-and-termination"></a>Инициализация и прекращение работы ядра базы данных DAO
При использовании объектов MFC DAO, ядро СУБД DAO сначала должен быть инициализирован и затем завершается перед приложением или библиотекой DLL завершает работу. Две функции `AfxDaoInit` и `AfxDaoTerm`, выполнять следующие задачи.  
  
### <a name="dao-database-engine-initialization-and-termination"></a>Инициализация и прекращение работы ядра базы данных DAO  
  
|||  
|-|-|  
|[AfxDaoInit](#afxdaoinit)|Инициализирует ядро СУБД DAO.|  
|[AfxDaoTerm](#afxdaoterm)|Завершает ядро СУБД DAO.|  
  
##  <a name="afxdaoinit"></a>AfxDaoInit  
 Эта функция инициализирует ядро СУБД DAO.  
  
```  
 
void AfxDaoInit();

throw(CDaoException*);  
```  
  
### <a name="remarks"></a>Примечания  
 В большинстве случаев нет необходимости вызывать `AfxDaoInit` так, как приложение автоматически вызывает его, когда он необходим.  
  
 Дополнительные сведения и пример вызова `AfxDaoInit`, в разделе [Технические заметки 54](../../mfc/tn054-calling-dao-directly-while-using-mfc-dao-classes.md).  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxdao.h  
  
##  <a name="afxdaoterm"></a>AfxDaoTerm  
 Эта функция завершает ядро СУБД DAO.  
  
```  
 
void AfxDaoTerm();  
```  
  
### <a name="remarks"></a>Примечания  
 Как правило достаточно вызвать эту функцию в обычной DLL MFC. приложение будет автоматически вызывать `AfxDaoTerm` когда он нужен.  
  
 В обычных библиотеках DLL MFC, вызовите `AfxDaoTerm` перед `ExitInstance` функции, но после уничтожения всех объектов MFC DAO.  
  
 Дополнительные сведения см. в разделе [Технические заметки 54](../../mfc/tn054-calling-dao-directly-while-using-mfc-dao-classes.md).  

### <a name="requirements"></a>Требования  
  **Заголовок** afxdao.h  

## <a name="see-also"></a>См. также  
 [Макросы и глобальные объекты](../../mfc/reference/mfc-macros-and-globals.md)
