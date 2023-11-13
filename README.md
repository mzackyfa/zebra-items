#### Berries API
Preview Code :
```js
function App() {
  const [datas, setDatas] = useState([])
  const [userSelect, setUserSelect] = useState("")
  const [isShow, setIsShow] = useState(false)

  const getBerries = async () => {
    const berries = await fetch("https://pokeapi.co/api/v2/berry/")
    const value = await berries.json()
    let result = value.results.map(data => {
      console.log(data)
      return {
        label: data.name,
        value: data.name
      }
    })
    setDatas(result.sort((a,b) => a.label.localeCompare(b.label)))
}
```
