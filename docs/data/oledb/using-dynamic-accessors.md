---
title: "Использование динамических методов доступа | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "методы доступа [C++], dynamic"
  - "динамические методы доступа"
ms.assetid: e5d5bfa6-2b1d-49d0-8ced-914666422431
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Использование динамических методов доступа
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Динамические методы доступа позволяют получить доступ к источнику данных, когда неизвестна схема базы данных \(базовая структура\).  Библиотека шаблонов OLE DB предоставляет несколько классов, чтобы помочь в этом.  
  
 Экземпляр [DynamicConsumer](http://msdn.microsoft.com/ru-ru/2ccc4c61-6749-4e83-aa81-00f8009c0dc3) показывает, как использовать классы методов доступа, чтобы получить информацию столбца и динамически создать методы доступа.  
  
## Использование CDynamicAccessor  
 [CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md) позволяет получить доступ к источнику данных, когда неизвестна схема базы данных \(базовая структура\).  Методы `CDynamicAccessor` получают информацию о столбцах, такую как имя столбца, количество и тип данных.  Информация о столбцах используется для динамического создания метода доступа во время выполнения.  Информация о столбцах хранится в буфере, созданном и управляемым данным классом.  Получить информацию можно с помощью метода [GetValue](../../data/oledb/cdynamicaccessor-getvalue.md).  
  
## Пример  
  
### Код  
  
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
  
## Использование CDynamicStringAccessor  
 [CDynamicStringAccessor](../../data/oledb/cdynamicstringaccessor-class.md) работает подобно [CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md), за исключением одного важного момента.  В отличие от `CDynamicAccessor`, который запрашивает данные в собственном формате поставщика, `CDynamicStringAccessor` запрашивает, чтобы поставщик делал выборку всех данных доступных из хранилища данных в виде данных строки.  Это особенно удобно для простых заданий, которые не требуют подсчета значений в хранилище данных, таких как отображение или распечатка содержимого хранилища данных.  
  
 Используйте методы `CDynamicStringAccessor` для получения информации о столбцах.  Информация о столбцах используется для динамического создания метода доступа во время выполнения.  Информация о столбцах хранится в буфере, созданном и управляемым данным классом.  Можно получить информацию из буфера с помощью [CDynamicStringAccessor::GetString](../Topic/CDynamicStringAccessor::GetString.md) или сохранить ее в буфере с помощью [CDynamicStringAccessor::SetString](../../data/oledb/cdynamicstringaccessor-setstring.md).  
  
## Пример  
  
### Код  
  
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
  
## Использование CDynamicParameterAccessor  
 [CDynamicParameterAccessor](../../data/oledb/cdynamicparameteraccessor-class.md) подобен [CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md), за исключением того, что `CDynamicParameterAccessor` получает информацию параметра, заданную с помощью вызова интерфейса [ICommandWithParameters](https://msdn.microsoft.com/en-us/library/ms712937.aspx).  Поставщик должен поддерживать `ICommandWithParameters`, чтобы поставщик мог использовать данный класс.  
  
 Информация параметра хранится в буфере, созданном и управляемым данным классом.  Получить данные параметра из буфера можно с помощью [CDynamicParameterAccessor::GetParam](../Topic/CDynamicParameterAccessor::GetParam.md) и [CDynamicParameterAccessor::GetParamType](../../data/oledb/cdynamicparameteraccessor-getparamtype.md).  
  
 Пример использования данного класса для выполнения процедуры, хранимой на SQL Server, и возвращения данных параметра, см. в статье базы знаний Майкрософт: Q058860 "Практическое руководство. Выполнение хранимых процедур с помощью CDynamicParameterAccessor". Статьи базы знаний доступны в документации по Visual Studio библиотеки MSDN или на [http:\/\/support.microsoft.com](http://support.microsoft.com/).  
  
## См. также  
 [Использование методов доступа](../../data/oledb/using-accessors.md)   
 [Класс CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md)   
 [Класс CDynamicStringAccessor](../../data/oledb/cdynamicstringaccessor-class.md)   
 [Класс CDynamicParameterAccessor](../../data/oledb/cdynamicparameteraccessor-class.md)   
 [DynamicConsumer Sample](http://msdn.microsoft.com/ru-ru/2ccc4c61-6749-4e83-aa81-00f8009c0dc3)