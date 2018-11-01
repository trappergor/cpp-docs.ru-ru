---
title: Инициализация и прекращение работы ядра базы данных DAO
ms.date: 11/04/2016
f1_keywords:
- vc.mfc.macros.data
helpviewer_keywords:
- DAO (Data Access Objects), termination
- DAO (Data Access Objects), initialization
ms.assetid: a7edf31c-e7c2-4f3e-aada-63c3e48781da
ms.openlocfilehash: ff924f0e0d599d447ef7dea0039de788d388d759
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50589635"
---
# <a name="dao-database-engine-initialization-and-termination"></a>Инициализация и прекращение работы ядра базы данных DAO

При работе с объектами MFC DAO, ядро базы данных DAO сначала должен быть инициализирован и затем завершается перед приложением или библиотекой DLL завершает работу. Две функции `AfxDaoInit` и `AfxDaoTerm`, выполнять эти задачи.

### <a name="dao-database-engine-initialization-and-termination"></a>Инициализация и прекращение работы ядра базы данных DAO

|||
|-|-|
|[AfxDaoInit](#afxdaoinit)|Инициализирует ядро базы данных DAO.|
|[AfxDaoTerm](#afxdaoterm)|Завершает ядро базы данных DAO.|

##  <a name="afxdaoinit"></a>  AfxDaoInit

Эта функция инициализирует ядро базы данных DAO.

```

void AfxDaoInit();

throw(CDaoException*);
```

### <a name="remarks"></a>Примечания

В большинстве случаев вам не нужно вызывать `AfxDaoInit` так, как приложение автоматически вызывает его, когда он необходим.

Дополнительные сведения и пример вызова `AfxDaoInit`, см. в разделе [технические 54 Примечание](../../mfc/tn054-calling-dao-directly-while-using-mfc-dao-classes.md).

### <a name="requirements"></a>Требования

  **Заголовок** afxdao.h

##  <a name="afxdaoterm"></a>  AfxDaoTerm

Эта функция завершает ядро базы данных DAO.

```

void AfxDaoTerm();
```

### <a name="remarks"></a>Примечания

Как правило требуется только для вызова этой функции в обычной MFC DLL. приложение будет автоматически вызывать `AfxDaoTerm` при необходимости.

В обычных библиотеках DLL MFC, вызовите `AfxDaoTerm` перед `ExitInstance` функции, но после будут уничтожены все объекты MFC DAO.

Дополнительные сведения см. в разделе [технические 54 Примечание](../../mfc/tn054-calling-dao-directly-while-using-mfc-dao-classes.md).

### <a name="requirements"></a>Требования

  **Заголовок** afxdao.h

## <a name="see-also"></a>См. также

[Макросы и глобальные объекты](../../mfc/reference/mfc-macros-and-globals.md)
