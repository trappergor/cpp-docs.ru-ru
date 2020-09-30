---
title: Использование динамических методов доступа
ms.date: 10/18/2018
helpviewer_keywords:
- accessors [C++], dynamic
- dynamic accessors
ms.assetid: e5d5bfa6-2b1d-49d0-8ced-914666422431
ms.openlocfilehash: eea1c6199fed5a4e6e331c1c76f34b96090b709a
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/29/2020
ms.locfileid: "91509413"
---
# <a name="using-dynamic-accessors"></a>Использование динамических методов доступа

Динамические методы доступа позволяют получить доступ к источнику данных, когда нет сведений о схеме базы данных (базовой структуре). Библиотека шаблонов OLE DB предоставляет несколько классов, которые помогут вам.

В образце [динамикконсумер](https://github.com/Microsoft/VCSamples/tree/master/VC2008Samples/ATL/OLEDB/Consumer/DynamicConsumer) показано, как использовать динамические классы методов доступа для получения сведений о столбцах и динамического создания методов доступа.

## <a name="using-cdynamicaccessor"></a>Использование CDynamicAccessor

[CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md) позволяет получить доступ к источнику данных, когда нет сведений о схеме базы данных (базовой структуре базы данных). `CDynamicAccessor` методы получают сведения о столбцах, такие как имена столбцов, количество и тип данных. Эти сведения о столбцах используются для динамического создания метода доступа во время выполнения. Сведения о столбцах хранятся в буфере, который создается и управляется этим классом. Получение данных из буфера с помощью метода [GetValue](./cdynamicaccessor-class.md#getvalue) .

## <a name="example"></a>Пример

```cpp
// Using_Dynamic_Accessors.cpp
// compile with: /c /EHsc
#include <stdio.h>
#include <objbase.h>
#include <atldbcli.h>

int main(int argc, char* argv[] )
{
    HRESULT hr = CoInitialize(NULL );

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

    hr = ss.Open(ds );
    hr = rs.Open(ss, "Shippers" );

    hr = rs.MoveFirst();
    while(SUCCEEDED(hr ) && hr != DB_S_ENDOFROWSET )
    {
        for(size_t i = 1; i <= rs.GetColumnCount(); i++ )
        {
            DBTYPE type;
            rs.GetColumnType(i, &type );
            printf_s( "Column %d [%S] is of type %d\n",
                      i, rs.GetColumnName(i ), type );

            switch(type )
            {
                case DBTYPE_WSTR:
                    printf_s( "value is %S\n",
                              (WCHAR*)rs.GetValue(i ) );
                break;
                case DBTYPE_STR:
                    printf_s( "value is %s\n",
                              (CHAR*)rs.GetValue(i ) );
                default:
                    printf_s( "value is %d\n",
                              *(long*)rs.GetValue(i ) );
            }
        }
        hr = rs.MoveNext();
    }

    rs.Close();
    ss.Close();
    ds.Close();
    CoUninitialize();

    return 0;
}
```

## <a name="using-cdynamicstringaccessor"></a>Использование CDynamicStringAccessor

[CDynamicStringAccessor](../../data/oledb/cdynamicstringaccessor-class.md) работает так же, как [CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md), за исключением одного важного пути. При `CDynamicAccessor` запросе данных в собственном формате, сообщаемом поставщиком, `CDynamicStringAccessor` запрашивает получение поставщиком всех данных, доступ к которым осуществляется из хранилища данных, в виде строковых данных. Этот процесс особенно полезен для простых задач, которые не нуждаются в вычислении значений в хранилище данных, например при отображении или печати содержимого хранилища данных.

Используйте `CDynamicStringAccessor` методы для получения сведений о столбцах. Эти сведения о столбцах используются для динамического создания метода доступа во время выполнения. Сведения о столбцах хранятся в буфере, созданном и управляемом этим классом. Получение данных из буфера с помощью [CDynamicStringAccessor:: GetString](./cdynamicstringaccessor-class.md#getstring) или сохранение их в буфер с помощью [CDynamicStringAccessor:: SetString](./cdynamicstringaccessor-class.md#setstring).

## <a name="example"></a>Пример

```cpp
// Using_Dynamic_Accessors_b.cpp
// compile with: /c /EHsc
#include <stdio.h>
#include <objbase.h>
#include <atldbcli.h>

int main(int argc, char* argv[] )
{
    HRESULT hr = CoInitialize(NULL );
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

    hr = ss.Open(ds );
    hr = rs.Open(ss, "Shippers" );

    hr = rs.MoveFirst();
    while(SUCCEEDED(hr ) && hr != DB_S_ENDOFROWSET )
    {
        for(size_t i = 1; i <= rs.GetColumnCount(); i++ )
        {
            printf_s( "column %d value is %s\n",
                      i, rs.GetString(i ) );
        }
        hr = rs.MoveNext();
    }

    rs.Close();
    ss.Close();
    ds.Close();
    CoUninitialize();

   return 0;
}
```

## <a name="using-cdynamicparameteraccessor"></a>Использование CDynamicParameterAccessor

[CDynamicParameterAccessor](../../data/oledb/cdynamicparameteraccessor-class.md) похож на [CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md), за исключением того, что `CDynamicParameterAccessor` получает сведения о параметрах, которые должны быть заданы путем вызова интерфейса [ICommandWithParameters](/sql/relational-databases/native-client-ole-db-interfaces/icommandwithparameters) . Для использования этого класса поставщик должен поддерживать интерфейс `ICommandWithParameters` для потребителя.

Сведения о параметрах хранятся в буфере, создаваемом и управляемом данным классом. Получение данных параметров из буфера с помощью [CDynamicParameterAccessor:: param](./cdynamicparameteraccessor-class.md#getparam) и [CDynamicParameterAccessor:: жетпарамтипе](./cdynamicparameteraccessor-class.md#getparamtype).

Пример использования этого класса для выполнения хранимой процедуры SQL Server и получения значений выходных параметров см. в примере кода [динамикконсумер](https://github.com/Microsoft/VCSamples/tree/master/VC2008Samples/ATL/OLEDB/Consumer/DynamicConsumer) в репозитории [Microsoft Вксамплес](https://github.com/Microsoft/VCSamples) на сайте GitHub.

## <a name="see-also"></a>См. также раздел

[Использование методов доступа](../../data/oledb/using-accessors.md)<br/>
[Класс CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md)<br/>
[Класс CDynamicStringAccessor](../../data/oledb/cdynamicstringaccessor-class.md)<br/>
[Класс CDynamicParameterAccessor](../../data/oledb/cdynamicparameteraccessor-class.md)<br/>
[Пример Динамикконсумер](https://github.com/Microsoft/VCSamples/tree/master/VC2008Samples/ATL/OLEDB/Consumer/DynamicConsumer)
