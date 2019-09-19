---
title: Инициализация и прекращение работы ядра базы данных DAO
ms.date: 09/17/2019
helpviewer_keywords:
- DAO (Data Access Objects), termination
- DAO (Data Access Objects), initialization
ms.assetid: a7edf31c-e7c2-4f3e-aada-63c3e48781da
ms.openlocfilehash: ccdf2e7b0f31576dddccad016e6b32806cdb82bf
ms.sourcegitcommit: 2f96e2fda591d7b1b28842b2ea24e6297bcc3622
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2019
ms.locfileid: "71095882"
---
# <a name="dao-database-engine-initialization-and-termination"></a>Инициализация и прекращение работы ядра базы данных DAO

DAO используется с базами данных Access и поддерживается в Office 2013. 3,6 является окончательной версией и считается устаревшей. При использовании объектов MFC DAO необходимо сначала инициализировать ядро СУБД DAO, а затем завершить работу, прежде чем приложение или библиотека DLL завершит работу. Две функции, `AfxDaoInit` и `AfxDaoTerm`, выполняют эти задачи.

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

В большинстве случаев вызывать `AfxDaoInit` не нужно, так как приложение автоматически вызывает его при необходимости.

Связанные сведения и пример вызова `AfxDaoInit`см. в [техническом примечании 54](../../mfc/tn054-calling-dao-directly-while-using-mfc-dao-classes.md).

### <a name="requirements"></a>Требования

  **Заголовок** афксдао. h

##  <a name="afxdaoterm"></a>афксдаотерм

Эта функция завершает работу компонента базы данных DAO.

```

void AfxDaoTerm();
```

### <a name="remarks"></a>Примечания

Как правило, эта функция должна вызываться только в обычной библиотеке DLL MFC. приложение будет автоматически вызываться `AfxDaoTerm` при необходимости.

В обычных библиотеках DLL MFC `AfxDaoTerm` вызовите `ExitInstance` метод перед функцией, но после уничтожения всех объектов MFC DAO.

Связанные сведения см. в [техническом примечании 54](../../mfc/tn054-calling-dao-directly-while-using-mfc-dao-classes.md).

### <a name="requirements"></a>Требования

  **Заголовок** афксдао. h

## <a name="see-also"></a>См. также

[Макросы и глобальные](../../mfc/reference/mfc-macros-and-globals.md)
