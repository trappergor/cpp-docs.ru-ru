---
title: Класс CDynamicStringAccessor | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CDynamicStringAccessor
- CDynamicStringAccessor.GetString
- CDynamicStringAccessor::GetString
- CDynamicStringAccessor::SetString
- CDynamicStringAccessor.SetString
dev_langs:
- C++
helpviewer_keywords:
- CDynamicStringAccessor class
- GetString method
- SetString method
ms.assetid: 138dc4de-c7c3-478c-863e-431e48249027
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: fd497c59bcdbaba2afc1571cf7509887a44bcd59
ms.sourcegitcommit: b217daee32d3413cf33753d9b4dc35a0022b1bfa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2018
ms.locfileid: "39233444"
---
# <a name="cdynamicstringaccessor-class"></a>Класс CDynamicStringAccessor
Позволяет доступ к источнику данных, когда схема базы данных (базовая структура).  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
      template< typename BaseType, DBTYPEENUM OleDbType >  
class CDynamicStringAccessorT : public CDynamicAccessor  
```  

  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldbcli.h 

## <a name="members"></a>Участники  
  
### <a name="methods"></a>Методы  
  
|||  
|-|-|  
|[GetString](#getstring)|Возвращает данные указанного столбца в виде строки.|  
|[SetString](#setstring)|Задает данные указанного столбца в виде строки.|  
  
## <a name="remarks"></a>Примечания  
 Хотя [CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md) запрашивает данные в собственном формате, Поставщик сообщил, что, `CDynamicStringAccessor` запросов, что поставщик получить все данные из хранилища данных в виде строковых данных. Это особенно полезно для простых задач, не требующих вычисления значений в хранилище данных, например отображением или печатью содержимого хранилища данных.  
  
 В собственный тип данных столбца в хранилище данных не имеет значения; до тех пор, пока поставщик поддерживает преобразование данных, он будет предоставлять данные в строковом формате. Если поставщик не поддерживает преобразование из собственного типа данных в строки (которая не часто), запрашивающим вызовом вернет значение success DB_S_ERRORSOCCURED и состояние для соответствующего столбца будет указывать на проблему преобразования с DBSTATUS_E_CANTCONVERTVALUE.  
  
 Используйте `CDynamicStringAccessor` методов, чтобы получить сведения о столбцах. Используйте эти сведения для столбца для динамического создания метода доступа во время выполнения.  
  
 Сведения о столбце хранится в буфере, создаваемом и управляемом данным классом. Получение данных из буфера с помощью [GetString](../../data/oledb/cdynamicstringaccessor-getstring.md), и не сохраняет в буфере с помощью [SetString](../../data/oledb/cdynamicstringaccessor-setstring.md).  
  
 Обсуждение и примеры использования классов динамического метода доступа, см. в разделе [с помощью динамических методов доступа](../../data/oledb/using-dynamic-accessors.md).  

## <a name="getstring"></a> CDynamicStringAccessor::GetString
Возвращает данные указанного столбца в виде строки.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
      BaseType* GetString(DBORDINAL nColumn) const throw();  

BaseType* GetString(const CHAR* pColumnName) const throw();  

BaseType* GetString(const WCHAR* pColumnName) const throw();  
```  
  
#### <a name="parameters"></a>Параметры  
 *nColumn*  
 [in] Номер столбца. Номера столбцов начинаются с 1. Значение 0 относится к столбцу закладку, если таковые имеются.  
  
 *pColumnName*  
 [in] Указатель на строку символов, которая содержит имя столбца.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на строковое значение, полученных из указанного столбца. Значение имеет тип `BaseType`, она будет называться **CHAR** или **WCHAR** в зависимости от того, определен ли _UNICODE. Возвращает значение NULL, если указанный столбец не найден.  
  
### <a name="remarks"></a>Примечания  
 Второй переопределяют форма принимает имя столбца в строку ANSI. Третий переопределить форма принимает имя столбца как строка Юникода.  
 
## <a name="setstring"></a> CDynamicStringAccessor::SetString
Задает данные указанного столбца в виде строки.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
HRESULT SetString(DBORDINAL nColumn,  
  BaseType* data) throw();  


HRESULT SetString(const CHAR* pColumnName,  
   BaseType* data) throw();  


HRESULT SetString(const WCHAR* pColumnName,  
   BaseType* data) throw();  
```  
  
#### <a name="parameters"></a>Параметры  
 *nColumn*  
 [in] Номер столбца. Номера столбцов начинаются с 1. Специальное значение 0 относится к столбцу закладку, если таковые имеются.  
  
 *pColumnName*  
 [in] Указатель на строку символов, которая содержит имя столбца.  
  
 *data*  
 [in] Указатель на строку данных для записи к указанному столбцу.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на строковое значение, которое задается указанного столбца. Значение имеет тип `BaseType`, она будет называться **CHAR** или **WCHAR** в зависимости от того, определен ли _UNICODE.  
  
### <a name="remarks"></a>Примечания  
 Второй переопределить форма принимает имя столбца в виде строки ANSI и третий переопределить форма принимает имя столбца в виде строки в Юникоде.  
  
 Если _SECURE_ATL определен должен иметь ненулевое значение, сбоя утверждения среды выполнения создается, если входные данные *данных* строки превышает допустимый максимум столбца данных, на которую указывает ссылка. В противном случае входная строка будет усечена, если он превышает максимально допустимую длину.  
  
## <a name="see-also"></a>См. также  
 [Шаблоны потребителей OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Ссылка на шаблоны OLE DB потребителя](../../data/oledb/ole-db-consumer-templates-reference.md)   
 [Класс CAccessor](../../data/oledb/caccessor-class.md)   
 [Класс CDynamicParameterAccessor](../../data/oledb/cdynamicparameteraccessor-class.md)   
 [Класс CManualAccessor](../../data/oledb/cmanualaccessor-class.md)   
 [Класс CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md)   
 [Класс CDynamicStringAccessorA](../../data/oledb/cdynamicstringaccessora-class.md)   
 [Класс CDynamicStringAccessorW](../../data/oledb/cdynamicstringaccessorw-class.md)   
 [Класс CXMLAccessor](../../data/oledb/cxmlaccessor-class.md)