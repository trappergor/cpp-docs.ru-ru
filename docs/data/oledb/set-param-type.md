---
title: "SET_PARAM_TYPE | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: SET_PARAM_TYPE
dev_langs: C++
helpviewer_keywords: SET_PARAM_TYPE macro
ms.assetid: 85979070-2d55-4c67-94b1-9b9058babc59
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: b8fb0ab344f5ee9e34c1157d661bced369afac41
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="setparamtype"></a>SET_PARAM_TYPE
Указывает макросы `COLUMN_ENTRY` , которые следуют за входными, выходными или и входными, и выходными макросами `SET_PARAM_TYPE` .  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
SET_PARAM_TYPE(  
type  
 )  
  
```  
  
#### <a name="parameters"></a>Параметры  
 `type`  
 [входные данные] Тип, задаваемый для параметра.  
  
## <a name="remarks"></a>Примечания  
 Поставщики поддерживают только входные и выходные типы параметров, поддерживаемые в базовом источнике данных. Тип представляет собой сочетание одного или нескольких значений **DBPARAMIO** (см. раздел [Структуры DBBINDING](https://msdn.microsoft.com/en-us/library/ms716845.aspx) в *справочнике программиста OLE DB*).  
  
-   **DBPARAMIO_NOTPARAM** Метод доступа не имеет параметров. Как правило, для **eParamIO** это значение задается в методах доступа к строкам, чтобы напомнить пользователям, что параметры игнорируются.  
  
-   **DBPARAMIO_INPUT** Входной параметр  
  
-   **DBPARAMIO_OUTPUT** Выходной параметр  
  
-   **DBPARAMIO_INPUT &#124; DBPARAMIO_OUTPUT** параметр является входным и выходным параметром.  
  
## <a name="example"></a>Пример  
```cpp  
class CArtistsProperty
{
public:
   short m_nReturn;
   short m_nAge;
   TCHAR m_szFirstName[21];
   TCHAR m_szLastName[31];

BEGIN_PARAM_MAP(CArtistsProperty)
   SET_PARAM_TYPE(DBPARAMIO_OUTPUT)
   COLUMN_ENTRY(1, m_nReturn)
   SET_PARAM_TYPE(DBPARAMIO_INPUT)
   COLUMN_ENTRY(2, m_nAge)
END_PARAM_MAP()

BEGIN_COLUMN_MAP(CArtistsProperty)
   COLUMN_ENTRY(1, m_szFirstName)
   COLUMN_ENTRY(2, m_szLastName)
END_COLUMN_MAP()

   HRESULT OpenDataSource()
   {
      CDataSource _db;
      _db.Open();
      return m_session.Open(_db);
   }

   void CloseDataSource()
   {
      m_session.Close();
   }

   CSession m_session;

   DEFINE_COMMAND_EX(CArtistsProperty, L" \
      { ? = SELECT Age FROM Artists WHERE Age < ? }")
};
``` 
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldbcli.h  
  
## <a name="see-also"></a>См. также  
 [Макросы и глобальные функции для шаблонов объектов-получателей OLE DB](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)