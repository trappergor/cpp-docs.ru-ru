---
title: Инициализация и прекращение работы ядра базы данных DAO
ms.date: 09/17/2019
helpviewer_keywords:
- DAO (Data Access Objects), termination
- DAO (Data Access Objects), initialization
ms.assetid: a7edf31c-e7c2-4f3e-aada-63c3e48781da
ms.openlocfilehash: 62460e8e55f70b8cb0743f1d044636d25121050d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365894"
---
# <a name="dao-database-engine-initialization-and-termination"></a>Инициализация и прекращение работы ядра базы данных DAO

DAO используется с базами данных Access и поддерживается в Office 2013. DAO 3.6 является окончательной версией, и он считается устаревшим. При использовании объектов MFC DAO движок базы данных DAO должен быть сначала инициализирован, а затем прекращен до завершения подачи заявки или DLL. Две функции, `AfxDaoInit` и, `AfxDaoTerm`выполнять эти задачи.

### <a name="dao-database-engine-initialization-and-termination"></a>Инициализация и прекращение работы ядра базы данных DAO

|||
|-|-|
|[AfxDaoInit](#afxdaoinit)|Инициализирует движок базы данных DAO.|
|[AfxDaoTerm](#afxdaoterm)|Прекращает работу движка базы данных DAO.|

## <a name="afxdaoinit"></a><a name="afxdaoinit"></a>AfxDaoInit

Эта функция инициализирует движок базы данных DAO.

```

void AfxDaoInit();

throw(CDaoException*);
```

### <a name="remarks"></a>Remarks

В большинстве случаев вам не `AfxDaoInit` нужно звонить, потому что приложение автоматически вызывает его, когда это необходимо.

Для получения соответствующей информации `AfxDaoInit`и для примера вызова см. [Technical Note 54](../../mfc/tn054-calling-dao-directly-while-using-mfc-dao-classes.md)

### <a name="requirements"></a>Требования

  **Заголовок** afxdao.h

## <a name="afxdaoterm"></a><a name="afxdaoterm"></a>AfxDaoTerm

Эта функция завершает работу движка базы данных DAO.

```

void AfxDaoTerm();
```

### <a name="remarks"></a>Remarks

Как правило, вам нужно только позвонить по этой функции в обычном MFC DLL; приложение автоматически звонит, `AfxDaoTerm` когда это необходимо.

В регулярных MFC DLLs звоните `AfxDaoTerm` перед функцией, `ExitInstance` но после того, как все объекты MFC DAO были уничтожены.

Для получения соответствующей информации [см.](../../mfc/tn054-calling-dao-directly-while-using-mfc-dao-classes.md)

### <a name="requirements"></a>Требования

  **Заголовок** afxdao.h

## <a name="see-also"></a>См. также раздел

[Макросы и глобальные объекты](../../mfc/reference/mfc-macros-and-globals.md)
