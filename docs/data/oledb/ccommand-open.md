---
title: "CCommand::Open | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL.CCommand.Open"
  - "ATL::CCommand::Open"
  - "CCommand.Open"
  - "CCommand::Open"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Open - метод"
ms.assetid: 4c9b8f31-faf3-452d-9a29-3d3e5f54d6f8
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# CCommand::Open
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Выполняется и при необходимости привязывает команду.  
  
## Синтаксис  
  
```  
  
      HRESULT Open(  
   const CSession& session,  
   LPCWSTR wszCommand,  
   DBPROPSET *pPropSet = NULL,  
   DBROWCOUNT* pRowsAffected = NULL,  
   REFGUID guidCommand = DBGUID_DEFAULT,  
   bool bBind = true,  
   ULONG ulPropSets = 0  
) throw( );  
HRESULT Open(  
   const CSession& session,  
   LPCSTR szCommand,  
   DBPROPSET *pPropSet = NULL,  
   DBROWCOUNT* pRowsAffected = NULL,  
   REFGUID guidCommand = DBGUID_DEFAULT,  
   bool bBind = true,  
   ULONG ulPropSets = 0  
) throw( );  
HRESULT Open(  
   const CSession& session,  
   INT szCommand = NULL,  
   DBPROPSET *pPropSet = NULL,  
   DBROWCOUNT* pRowsAffected = NULL,  
   REFGUID guidCommand = DBGUID_DEFAULT,  
   bool bBind = true,  
   ULONG ulPropSets = 0  
) throw( );  
HRESULT Open(  
   DBPROPSET *pPropSet = NULL,  
   DBROWCOUNT* pRowsAffected = NULL,  
   bool bBind = true,  
   ULONG ulPropSets = 0  
) throw( );  
```  
  
#### Параметры  
 `session`  
 \[in\] сеанс, в котором для выполнения команды.  
  
 `wszCommand`  
 \[in\] команды выполнения, переданные как строки юникода.  Может быть **NULL** при использовании `CAccessor`, в случае которого команда будет извлечена из значения, передаваемого в макрос [DEFINE\_COMMAND](../../data/oledb/define-command.md).  В разделе [ICommand::Execute](https://msdn.microsoft.com/en-us/library/ms718095.aspx) справочника *программиста OLE DB* для сведения.  
  
 `szCommand`  
 \[in\] то же, `wszCommand` за исключением того, что этот параметр принимает командную строку ANSI.  Четвертая форму этого метода может принимать значение NULL.  В разделе «примечания» далее в этом разделе для сведения.  
  
 *pPropSet*  
 \[in\] указатель на массив структур [DBPROPSET](https://msdn.microsoft.com/en-us/library/ms714367.aspx), содержащий свойства и значения, используемые для задания.  В разделе [Наборы свойств и группы свойств](https://msdn.microsoft.com/en-us/library/ms713696.aspx) справочника *программиста по OLE DB* в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `pRowsAffected`  
 \[In\/out\] указатель на адрес памяти, возвращается число строк, затронутых командой.  Если *\*pRowsAffected***NULL**, количество строк не возвращается.  В противном случае **Открыть** задает \*`pRowsAffected` в соответствии с следующим условиям:  
  
|If|То|  
|--------|--------|  
|Элемент **cParamSets**`pParams` более 1|\*`pRowsAffected` представляет общее число строк, затронутых всеми наборами параметров, определенные на выполнение.|  
|Число затронутых строк недоступно|\*`pRowsAffected` имеет значение — 1.|  
|Команда не обновляется, не будет удалять или не вставляет строки|\*`pRowsAffected` не определено.|  
  
 `guidCommand`  
 \[in\] идентификатор GUID, определяющий синтаксис и общие правила для поставщика использовать при анализе текст команды.  См. в разделах [ICommandText::GetCommandText](https://msdn.microsoft.com/en-us/library/ms709825.aspx) и [ICommandText::SetCommandText](https://msdn.microsoft.com/en-us/library/ms709757.aspx) справочника *программиста OLE DB* для сведения.  
  
 `bBind`  
 \[in\] указывает ли привязка команды автоматически после его выполнять.  Значение по умолчанию **true**, которое вызывает команду быть привязанным автоматически.  Параметр `bBind` в **false** предотвращает автоматическую привязку команды, чтобы можно было выполнить вручную. \(Ручная привязка представляет особый интерес для пользователей OLAP\).  
  
 `ulPropSets`  
 \[in\] количество структур [DBPROPSET](https://msdn.microsoft.com/en-us/library/ms714367.aspx), переданных в аргумент *pPropSet*.  
  
## Возвращаемое значение  
 Стандартное `HRESULT`.  
  
## Заметки  
 Первые 3 формы **Открыть** имеют сеанс, команды создают и выполняют команду, привязку все параметры по мере необходимости.  
  
 Первая форма **Открыть** принимает командную строку юникода и не имеет значения по умолчанию.  
  
 Вторая форма **Открыть** не выполняет командную строку ANSI и отсутствует значение по умолчанию \(требуемые для обратной совместимости с существующими приложениями ANSI\).  
  
 Третья форму **Открыть** позволяет командной строки, чтобы быть NULL, из\-за типа `int` со значением по умолчанию NULL.  Предоставляется для вызова `Open(session, NULL);` или `Open(session);`, поскольку NULL типа `int`.  Эта версия требует и подтверждает параметр `int` NULL.  
  
 Используйте четвертую форму **Открыть**, если уже создана команда и необходимо выполнить одно [Подготовка](../../data/oledb/ccommand-prepare.md) и несколько сред выполнения.  
  
> [!NOTE]
>  **Открыть** вызывает метод **Выполнить**, который в свою очередь, вызывает `GetNextResult`.  
  
## Требования  
 **Заголовок:** atldbcli.h  
  
## См. также  
 [Класс CCommand](../../data/oledb/ccommand-class.md)