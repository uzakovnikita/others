const deps1 = {
  mongo: [],
  tzinfo: ['thread_safe'],
  uglifier: ['execjs'],
  execjs: ['thread_safe', 'json'],
  redis: [],
  thread_safe: [],
  json: []
};
const ex = (deps) => {
  const result = []; // для записи результатов
  const used = []; // смотрим куда ходили
  const dfs = (vertex, deps, used) => { // алгоритм поиска в глубину с доп нагрузкой
    used.push(vertex);
    for (const dep of deps[vertex]) {
      if (!used.includes(dep)) {
        dfs(dep, deps, used)
      }
    }
    result.push(vertex) // сама доп нагрузка
  }
  for (const iter in deps) {
    if (!used.includes(iter)) { // для работы со списком смежности необходимо делать такой перебор. потому что не все компоненты могут быть связаны между собой(несколько компонент связности в графе)
      dfs(iter, deps, used)
    }

  }
  return result;
};
ex(deps1)
