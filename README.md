# 📋 Sobre o projeto
### O projeto dos `snippets` foi criado com o objetivo de ajudar a todos os devs em php que utilizam do framework <b>Laminas</b>.. o antigo <b>Zend</b>, mas claro que ele não serve apenas para essa galera, o projeto tambem se adequa aqueles que buscam mais agilidade na hora de debugar e escrever seus códigos.

## ✅ Os snippets que a extenção atual possui são:


### 📌 Select completo com o laminas
- sqlc 
``` 
$sql    = new Sql($this->$var);
$select = $sql->select();
$where  = new Where();

// $where;

$select->from(['t'=>'table'])
->where($where);

$rows = [];

$rs = $sql->prepareStatementForSqlObject($select)->execute();

foreach($rs as $ln)
{
    $rows[] = $ln;
}

return $rows;
```
### 📌 Select de apenas um campo com o laminas
- sqlm
``` 
$sql    = new Sql($this->$var);
$select = $sql->select();
$where  = new Where();

// $where;

$select->from(['t'=>'table'])
->where($where);

return $sql->prepareStatementForSqlObject($select)->execute()->current();
```

### 📌 Select para verificação de registro, retornando um valor booleano
- sqlbool
``` 
$sql    = new Sql($this->$var);
$select = $sql->select();
$where  = new Where();

// $where;

$select->from(['t'=>'table'])
->where($where);

return $sql->prepareStatementForSqlObject($select)->execute()->count() > 0 ? true : false;
```

### 📌 Update simples com o laminas
- sqlu
``` 
$sql   = new Sql($this->variable);
$where = new Where();

$where->equalTo('value','value');

$update = $sql->update('table')
->set([
    'column' => 'value'
])
->where($where);

$sql->prepareStatementForSqlObject($update)->execute();
```

### 📌 Create a private function
- privf
``` 
    private function Test()
    {
        // code...
    }
```

### 📌 Create a public function
- pubf
``` 
    public function Test()
    {
        // code...
    }
```

### 📌 Retorna a string do select com o laminas

- sqlbs ```echo '<pre>'; var_dump($sql->buildSqlString($select)); die();```

## 📌 Outros

- ifsem
``` 
if(isset($foo) && !empty($foo))
{
    return $foo;
}
```

- php  `<?php  ?>`
- ephp `<?=    ?>`
- cphp `?>     <?php`
- issem  `(isset($v) && !empty($v) ? true : false)`
- dd     `echo '<pre>'; var_dump($v) die(); `
- decode `mb_convert_encoding($v, 'UTF-8', 'ISO-8859-1')`
