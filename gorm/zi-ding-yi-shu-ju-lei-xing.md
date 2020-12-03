# 自定义数据类型

> [https://gorm.io/zh\_CN/docs/data\_types.html](https://gorm.io/zh_CN/docs/data_types.html)

## 简述

> 1. 定义数据类型的Scanner / Valuer
> 2. ```
>    type JSON json.RawMessage
>
>    // 实现 sql.Scanner 接口，Scan 将 value 扫描至 Jsonb
>    func (j *JSON) Scan(value interface{}) error {
>      bytes, ok := value.([]byte)
>      if !ok {
>        return errors.New(fmt.Sprint("Failed to unmarshal JSONB value:", value))
>      }
>
>      result := json.RawMessage{}
>      err := json.Unmarshal(bytes, &result)
>      *j = JSON(result)
>      return err
>    }
>
>    // 实现 driver.Valuer 接口，Value 返回 json value
>    func (j JSON) Value() (driver.Value, error) {
>      if len(j) == 0 {
>        return nil, nil
>      }
>      return json.RawMessage(j).MarshalJSON()
>    }
>    ```

## 查询

> [https://blog.csdn.net/moshowgame/article/details/81016482](https://blog.csdn.net/moshowgame/article/details/81016482)



