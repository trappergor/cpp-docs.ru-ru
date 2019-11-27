---
title: Инициализация и прекращение работы ядра базы данных DAO
ms.date: 09/17/2019
helpviewer_keywords:
- DAO (Data Access Objects), termination
- DAO (Data Access Objects), initialization
ms.assetid: a7edf31c-e7c2-4f3e-aada-63c3e48781da
ms.openlocfilehash: 24a24d5a81da18d01472fc760c2adf96ee9868d5
ms.sourcegitcommit: 069e3833bd821e7d64f5c98d0ea41fc0c5d22e53
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2019
ms.locfileid: "74303466"
---
# <a name="dao-database-engine-initialization-and-termination"></a>Инициализация и прекращение работы ядра базы данных DAO

DAO используется с базами данных Access и поддерживается в Office 2013. Версия DAO 3,6 является окончательной и считается устаревшей. При использовании объектов MFC DAO необходимо сначала инициализировать ядро СУБД DAO, а затем завершить работу, прежде чем приложение или библиотека DLL завершит работу. Эти задачи выполняют две функции: `AfxDaoInit` и `AfxDaoTerm`.

### <a name="dao-database-engine-initialization-and-termination"></a>Инициализация и прекращение работы ядра базы данных DAO

|||
|-|-|
|[афксдаоинит](#afxdaoinit)|Инициализирует ядро базы данных DAO.|
|[афксдаотерм](#afxdaoterm)|Завершает работу компонента базы данных DAO.|

##  <a name="afxdaoinit"></a>афксдаоинит

Эта функция инициализирует ядро базы данных DAO.

```

void AfxDaoInit();

throw(CDaoException*);
```

### <a name="remarks"></a>Примечания

В большинстве случаев нет необходимости вызывать `AfxDaoInit`, так как приложение автоматически вызывает его при необходимости.

Связанные сведения и пример вызова `AfxDaoInit`см. в [техническом примечании 54](../../mfc/tn054-calling-dao-directly-while-using-mfc-dao-classes.md).

### <a name="requirements"></a>Требования

  **Заголовок** афксдао. h

##  <a name="afxdaoterm"></a>афксдаотерм

Эта функция завершает работу компонента базы данных DAO.

```

void AfxDaoTerm();
```

### <a name="remarks"></a>Примечания

Как правило, эта функция должна вызываться только в обычной библиотеке DLL MFC. приложение автоматически вызывает `AfxDaoTerm`, когда это необходимо.

В обычных библиотеках DLL MFC вызовите `AfxDaoTerm` перед функцией `ExitInstance`, но после уничтожения всех объектов MFC DAO.

Связанные сведения см. в [техническом примечании 54](../../mfc/tn054-calling-dao-directly-while-using-mfc-dao-classes.md).

### <a name="requirements"></a>Требования

  **Заголовок** афксдао. h

## <a name="see-also"></a>См. также:

[Макросы и глобальные](../../mfc/reference/mfc-macros-and-globals.md)
