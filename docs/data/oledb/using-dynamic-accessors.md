---
title: "Использование динамических методов доступа | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- accessors [C++], dynamic
- dynamic accessors
ms.assetid: e5d5bfa6-2b1d-49d0-8ced-914666422431
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: b3d2e722ce96ff7a2f1add779377079a0eaecfc6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="using-dynamic-accessors"></a>Использование динамических методов доступа
Динамические методы доступа позволяют доступ к источнику данных, когда схема базы данных (базовая структура). Библиотека шаблонов OLE DB предоставляет несколько классов, которые помогут вам сделать это.  
  
 [DynamicConsumer](http://msdn.microsoft.com/en-us/2ccc4c61-6749-4e83-aa81-00f8009c0dc3) образце показано, как использовать классы динамического метода доступа, чтобы получить сведения о столбцах и динамически создать методы доступа.  
  
## <a name="using-cdynamicaccessor"></a>С помощью CDynamicAccessor  
 [CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md) дает возможность доступа к источнику данных, если у вас нет сведений о схеме базы данных (базовая структура). `CDynamicAccessor`методы получают информацию о столбцах, такие как имена столбцов, число и тип данных. Используйте эти сведения для столбца для динамического создания метода доступа во время выполнения. Сведения о столбце хранится в буфере, который создается и управляется этим классом. Получить данные из буфера с помощью [GetValue](../../data/oledb/cdynamicaccessor-getvalue.md) метод.  
  
## <a name="example"></a>Пример  
  
### <a name="code"></a>Код  
  
```  
// Using_Dynamic_Accessors.cpp  
// compile with: /c /EHsc  
#include <stdio.h>  
#include <objbase.h>  
#include <atldbcli.h>  
  
int main( int argc, char* argv[] )  
{  
    HRESULT hr = CoInitialize( NULL );  
  
    CDataSource ds;  
    CSession ss;  
  
    CTable<CDynamicAccessor> rs;  
  
    // The following is an example initialization string:  
    hr = ds.OpenFromInitializationString(L"Provider=SQLOLEDB.1;"  
      L"Integrated Security=SSPI;Persist Security Info=False;"  
      L"Initial Catalog=Loginname;Data Source=your_data_source;"  
      L"Use Procedure for Prepare=1;Auto Translate=True;"  
      L"Packet Size=4096;Workstation ID=LOGINNAME01;"  
      L"Use Encryption for Data=False;"  
      L"Tag with column collation when possible=False");  
  
    hr = ss.Open( ds );  
    hr = rs.Open( ss, "Shippers" );  
  
    hr = rs.MoveFirst( );  
    while( SUCCEEDED( hr ) && hr != DB_S_ENDOFROWSET )  
    {  
        for( size_t i = 1; i <= rs.GetColumnCount( ); i++ )  
        {  
            DBTYPE type;  
            rs.GetColumnType( i, &type );  
            printf_s( "Column %d [%S] is of type %d\n",  
                      i, rs.GetColumnName( i ), type );   
  
            switch( type )  
            {  
                case DBTYPE_WSTR:  
                    printf_s( "value is %S\n",  
                              (WCHAR*)rs.GetValue( i ) );  
                break;  
                case DBTYPE_STR:  
                    printf_s( "value is %s\n",  
                              (CHAR*)rs.GetValue( i ) );  
                default:  
                    printf_s( "value is %d\n",  
                              *(long*)rs.GetValue( i ) );  
            }  
        }  
        hr = rs.MoveNext( );  
    }  
  
    rs.Close();     
    ss.Close();  
    ds.Close();  
    CoUninitialize();  
  
    return 0;  
}  
```  
  
## <a name="using-cdynamicstringaccessor"></a>С помощью CDynamicStringAccessor  
 [CDynamicStringAccessor](../../data/oledb/cdynamicstringaccessor-class.md) работает как [CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md), за исключением одно важное отличие. Хотя `CDynamicAccessor` запрашивает данные в собственном формате, полученных от поставщика `CDynamicStringAccessor` запросов, что поставщик извлечь все данные из хранилища данных в виде строковых данных. Это особенно полезно для простых задач, не требующих вычисления значений в хранилище данных, таких как отображение или Печать содержимого хранилища данных.  
  
 Используйте `CDynamicStringAccessor` методов, чтобы получить сведения о столбцах. Используйте эти сведения для столбца для динамического создания метода доступа во время выполнения. Сведения о столбце хранится в буфере, созданном и управляемым данным классом. Получить данные из буфера с помощью [CDynamicStringAccessor::GetString](../../data/oledb/cdynamicstringaccessor-getstring.md) или сохраните ее в буфер с помощью [CDynamicStringAccessor::SetString](../../data/oledb/cdynamicstringaccessor-setstring.md).  
  
## <a name="example"></a>Пример  
  
### <a name="code"></a>Код  
  
```  
// Using_Dynamic_Accessors_b.cpp  
// compile with: /c /EHsc  
#include <stdio.h>  
#include <objbase.h>  
#include <atldbcli.h>  
  
int main( int argc, char* argv[] )  
{  
    HRESULT hr = CoInitialize( NULL );  
    if (hr != S_OK)  
    {  
        exit (-1);  
    }  
  
    CDataSource ds;  
    CSession ss;  
  
    CTable<CDynamicStringAccessor> rs;  
  
    // The following is an example initialization string:  
    hr = ds.OpenFromInitializationString(L"Provider=SQLOLEDB.1;"  
      L"Integrated Security=SSPI;Persist Security Info=False;"  
      L"Initial Catalog=Loginname;Data Source=your_data_source;"  
      L"Use Procedure for Prepare=1;Auto Translate=True;"  
      L"Packet Size=4096;Workstation ID=LOGINNAME01;"  
      L"Use Encryption for Data=False;"  
      L"Tag with column collation when possible=False");  
  
    hr = ss.Open( ds );  
    hr = rs.Open( ss, "Shippers" );  
  
    hr = rs.MoveFirst( );  
    while( SUCCEEDED( hr ) && hr != DB_S_ENDOFROWSET )  
    {  
        for( size_t i = 1; i <= rs.GetColumnCount( ); i++ )  
        {  
            printf_s( "column %d value is %s\n",   
                      i, rs.GetString( i ) );  
        }  
        hr = rs.MoveNext( );  
    }  
  
    rs.Close();     
    ss.Close();  
    ds.Close();  
    CoUninitialize();  
  
   return 0;  
  
}  
```  
  
## <a name="using-cdynamicparameteraccessor"></a>С помощью CDynamicParameterAccessor  
 [CDynamicParameterAccessor](../../data/oledb/cdynamicparameteraccessor-class.md) аналогичен [CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md), за исключением того, что `CDynamicParameterAccessor` получает сведения о параметрах для задания, вызвав [ICommandWithParameters](https://msdn.microsoft.com/en-us/library/ms712937.aspx) интерфейс. Для использования этого класса поставщик должен поддерживать интерфейс `ICommandWithParameters` для потребителя.  
  
 Сведения о параметрах хранятся в буфере, создаваемом и управляемом данным классом. Получить данные параметров из буфера с помощью [CDynamicParameterAccessor::GetParam](../../data/oledb/cdynamicparameteraccessor-getparam.md) и [CDynamicParameterAccessor::GetParamType](../../data/oledb/cdynamicparameteraccessor-getparamtype.md).  
  
 Пример, демонстрирующий использование этого класса для выполнения хранимой процедуры SQL Server и получения значений выходных параметров, см. в статье базы знаний Q058860, HOWTO: Execute Stored Procedure using CDynamicParameterAccessor (Практическое руководство. Выполнение хранимой процедуры с помощью метода CDynamicParameterAccessor). Статьи базы знаний доступны в документации по Visual Studio библиотеки MSDN или в [http://support.microsoft.com](http://support.microsoft.com/).  
  
## <a name="see-also"></a>См. также  
 [Использование методов доступа](../../data/oledb/using-accessors.md)   
 [CDynamicAccessor-класс](../../data/oledb/cdynamicaccessor-class.md)   
 [Класс CDynamicStringAccessor](../../data/oledb/cdynamicstringaccessor-class.md)   
 [Класс CDynamicParameterAccessor](../../data/oledb/cdynamicparameteraccessor-class.md)   
 [Образец DynamicConsumer](http://msdn.microsoft.com/en-us/2ccc4c61-6749-4e83-aa81-00f8009c0dc3)