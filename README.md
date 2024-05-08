# frontend_api_call
# we use axios for api call in frontend
# npm i axios

import axios from 'axios';
const Signup = () => {
//state for set username
  const[userName,setuserName] = useState('');
  

  //state for set password
  const[password,setPassword] = useState('');

  const handleApi = () =>{
    console.log({userName,password});
    // for call apis for post api
    const url ='http://localhost:4000/signup';
    const data ={userName,password};

    axios.post(url,data)
    .then((res)=>{ console.log(res)})
    .catch((err)=>{ console.log("err in the api",err)})

  }
  
  return (
    <div>
      Welcome To Sign Up
        <br/>
        USER NAME
        <input type='text' value={userName} 
        onChange={(e)=>{
            setuserName(e.target.value);
        }}/>
        <br/>
        PASS WORD
        <input type='text' value={password} onChange={(e)=>{
          setPassword(e.target.value)
        }}/>
        <br/>
        <button onClick={handleApi}> Submit </button>
        <Link to="/login">LOGIN</Link>

    </div>
  )
}

export default Signup
