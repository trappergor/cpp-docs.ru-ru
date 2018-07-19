---
title: Инициализация ядра базы данных DAO и прекращение работы | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.mfc.macros.data
dev_langs:
- C++
helpviewer_keywords:
- DAO (Data Access Objects), termination
- DAO (Data Access Objects), initialization
ms.assetid: a7edf31c-e7c2-4f3e-aada-63c3e48781da
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3f28c0c166bcbf13181161d6afce484fe4a45b80
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33369906"
---
# <a name="dao-database-engine-initialization-and-termination"></a>Инициализация и прекращение работы ядра базы данных DAO
При использовании объектов MFC DAO, ядро СУБД DAO сначала должен быть инициализирован и затем завершается перед приложением или библиотекой DLL завершает работу. Две функции `AfxDaoInit` и `AfxDaoTerm`, выполнять следующие задачи.  
  
### <a name="dao-database-engine-initialization-and-termination"></a>Инициализация и прекращение работы ядра базы данных DAO  
  
|||  
|-|-|  
|[AfxDaoInit](#afxdaoinit)|Инициализирует ядро СУБД DAO.|  
|[AfxDaoTerm](#afxdaoterm)|Завершает ядро СУБД DAO.|  
  
##  <a name="afxdaoinit"></a>  AfxDaoInit  
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
  
##  <a name="afxdaoterm"></a>  AfxDaoTerm  
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
