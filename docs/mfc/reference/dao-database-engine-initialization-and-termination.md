---
title: "Инициализация ядра базы данных DAO и завершение | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
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
caps.latest.revision: 13
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: b6119279234558998fad1f220239a29618c69cc5
ms.lasthandoff: 02/24/2017

---
# <a name="dao-database-engine-initialization-and-termination"></a>Инициализация и прекращение работы ядра базы данных DAO
При использовании объектов MFC DAO, ядро базы данных DAO сначала должен быть инициализирован и затем завершается перед приложением или библиотекой DLL завершает работу. Две функции `AfxDaoInit` и `AfxDaoTerm`, выполнять эти задачи.  
  
### <a name="dao-database-engine-initialization-and-termination"></a>Инициализация и прекращение работы ядра базы данных DAO  
  
|||  
|-|-|  
|[AfxDaoInit](#afxdaoinit)|Инициализирует ядро базы данных DAO.|  
|[AfxDaoTerm](#afxdaoterm)|Завершает ядро базы данных DAO.|  
  
##  <a name="a-nameafxdaoinita--afxdaoinit"></a><a name="afxdaoinit"></a>AfxDaoInit  
 Эта функция инициализирует ядро базы данных DAO.  
  
```  
 
void AfxDaoInit();

throw(CDaoException*);  
```  
  
### <a name="remarks"></a>Примечания  
 В большинстве случаев нет необходимости вызывать `AfxDaoInit` потому, что приложение автоматически вызывает его, когда он нужен.  
  
 Дополнительные сведения и пример вызова `AfxDaoInit`, в разделе [Технические заметки 54](../../mfc/tn054-calling-dao-directly-while-using-mfc-dao-classes.md).  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxdao.h  
  
##  <a name="a-nameafxdaoterma--afxdaoterm"></a><a name="afxdaoterm"></a>AfxDaoTerm  
 Эта функция завершает ядро базы данных DAO.  
  
```  
 
void AfxDaoTerm();  
```  
  
### <a name="remarks"></a>Примечания  
 Как правило достаточно вызвать эту функцию в обычной библиотеке DLL; приложение будет автоматически вызывать `AfxDaoTerm` когда он нужен.  
  
 В обычных библиотеках DLL, вызовите `AfxDaoTerm` перед `ExitInstance` функции, но после были уничтожены все объекты MFC DAO.  
  
 Дополнительные сведения см. в разделе [Технические заметки 54](../../mfc/tn054-calling-dao-directly-while-using-mfc-dao-classes.md).  

### <a name="requirements"></a>Требования  
  **Заголовок** afxdao.h  

## <a name="see-also"></a>См. также  
 [Макросы и глобальные объекты](../../mfc/reference/mfc-macros-and-globals.md)

