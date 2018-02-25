---
title: "CCommand::Open | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL.CCommand.Open
- ATL::CCommand::Open
- CCommand.Open
- CCommand::Open
dev_langs:
- C++
helpviewer_keywords:
- Open method
ms.assetid: 4c9b8f31-faf3-452d-9a29-3d3e5f54d6f8
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: bf4d30382224cd1fe85d12623acdcb90b0dee1bd
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
---
# <a name="ccommandopen"></a>CCommand::Open
Выполняет и при необходимости привязывает команды.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
HRESULT Open(const CSession& session,  
   LPCWSTR wszCommand,  
   DBPROPSET *pPropSet = NULL,  
   DBROWCOUNT* pRowsAffected = NULL,  
   REFGUID guidCommand = DBGUID_DEFAULT,  
   bool bBind = true,  
   ULONG ulPropSets = 0) throw();  


HRESULT Open(const CSession& session,  
   LPCSTR szCommand,  
   DBPROPSET *pPropSet = NULL,  
   DBROWCOUNT* pRowsAffected = NULL,  
   REFGUID guidCommand = DBGUID_DEFAULT,  
   bool bBind = true,  
   ULONG ulPropSets = 0) throw();  


HRESULT Open(const CSession& session,  
   INT szCommand = NULL,  
   DBPROPSET *pPropSet = NULL,  
   DBROWCOUNT* pRowsAffected = NULL,  
   REFGUID guidCommand = DBGUID_DEFAULT,  
   bool bBind = true,  
   ULONG ulPropSets = 0) throw();  


HRESULT Open(DBPROPSET *pPropSet = NULL,  
   DBROWCOUNT* pRowsAffected = NULL,  
   bool bBind = true,  
   ULONG ulPropSets = 0) throw();  
```  
  
#### <a name="parameters"></a>Параметры  
 `session`  
 [in] Сеанс, в которой выполняется команда.  
  
 `wszCommand`  
 [in] Команда для выполнения, передается как строка Юникода. Может быть **NULL** при использовании `CAccessor`, в этом случае команда извлекается из значения, переданного [DEFINE_COMMAND](../../data/oledb/define-command.md) макрос. В разделе [ICommand::Execute](https://msdn.microsoft.com/en-us/library/ms718095.aspx) в *Справочник программиста OLE DB* подробные сведения.  
  
 `szCommand`  
 [in] То же, что `wszCommand` за исключением того, что этот параметр принимает командной строки ANSI. Четвертый виде этот метод может принимать значение NULL. В разделе «Примечания» далее в этом разделе сведения.  
  
 *pPropSet*  
 [in] Указатель на массив [DBPROPSET](https://msdn.microsoft.com/en-us/library/ms714367.aspx) структур, содержащих свойства и значения, задаваемые. В разделе [наборов свойств и группы свойств](https://msdn.microsoft.com/en-us/library/ms713696.aspx) в *справочника программиста OLE DB* в Windows SDK.  
  
 `pRowsAffected`  
 [входные/выходные] Указатель на область памяти, где возвращается число строк, затронутых командой. Если  *\*pRowsAffected* — **NULL**, количество строк не возвращается. В противном случае **откройте** задает *`pRowsAffected` на следующих условиях:  
  
|If|Следующее действие|  
|--------|----------|  
|**CParamSets** элемент `pParams` больше 1|*`pRowsAffected` Представляет общее число строк, затронутых всеми наборов параметров, указанных в этом выполнении.|  
|Количество затронутых строк недоступен|*`pRowsAffected` имеет значение -1.|  
|Команда не обновления, удаления или вставки строк|*`pRowsAffected` не определено.|  
  
 `guidCommand`  
 [in] GUID, который определяет синтаксис и общие правила для поставщика, используемого при синтаксическом анализе текста команды. В разделе [ICommandText::GetCommandText](https://msdn.microsoft.com/en-us/library/ms709825.aspx) и [ICommandText::SetCommandText](https://msdn.microsoft.com/en-us/library/ms709757.aspx) в *Справочник программиста OLE DB* подробные сведения.  
  
 `bBind`  
 [in] Указывает, нужно ли привязывать команда автоматически после выполнения. Значение по умолчанию — **true**, что вызывает команду, чтобы автоматически привязать. Установка `bBind` для **false** предотвращает автоматическое привязку команды, таким образом, можно привязать вручную. (Ручной привязки — особый интерес для пользователей OLAP).  
  
 `ulPropSets`  
 [in] Число [DBPROPSET](https://msdn.microsoft.com/en-us/library/ms714367.aspx) структуры, передаются в *pPropSet* аргумент.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Стандартный `HRESULT`.  
  
## <a name="remarks"></a>Примечания  
 Первые три вида **откройте** занять сеанса, создания команды и выполнения команды, привязки параметров при необходимости.  
  
 Первая форма **откройте** принимает командной строки в Юникоде и нет значения по умолчанию.  
  
 Во второй форме **откройте** принимает командной строки ANSI и значения по умолчанию (предоставляется для обеспечения обратной совместимости с существующими приложениями ANSI).  
  
 Третий вид **откройте** позволяет принимать значение NULL, из-за типа строку команды `int` со значением по умолчанию NULL. Он предоставляется для вызова `Open(session, NULL);` или `Open(session);` так как значение NULL тип `int`. Эта версия требует и подтверждает, что `int` параметр иметь значение NULL.  
  
 Используйте четвертый форму **откройте** при создании команды и необходимо выполнить один [Подготовка](../../data/oledb/ccommand-prepare.md) и выполнения нескольких.  
  
> [!NOTE]
>  **Откройте** вызовы **Execute**, который в свою очередь вызывает `GetNextResult`.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldbcli.h  
  
## <a name="see-also"></a>См. также  
 [Класс CCommand](../../data/oledb/ccommand-class.md)