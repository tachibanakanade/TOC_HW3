import java.net.*;
import java.io.*;
import org.json.*;
import java.util.*;


public class TocHw3 {
	public static void main(String[] args) throws JSONException {
		// TODO Auto-generated method stub
		String comparedYear = "", listedYear = "";
		int avg_price, amount = 0, count = 0;
		
		try 
		{
			URL url = new URL(args[0]);
			URLConnection connect = url.openConnection();
			InputStreamReader isr = new InputStreamReader(connect.getInputStream(), "UTF-8");
			JSONArray jsonRealPrice = new JSONArray(new JSONTokener(isr));
			//JSONArray jsonRealPrice = new JSONArray(new JSONTokener(new FileReader(new File("5365dee31bc6e9d9463a0057.json"))));
			for(int i = 0 ; i < jsonRealPrice.length() ; i++)
			{
				for(int j = Integer.parseInt(args[3]) ; j <= 103 ; j++)
				{
					comparedYear = "" + j;
					listedYear = "" + jsonRealPrice.getJSONObject(i).getInt("交易年月");
					if(jsonRealPrice.getJSONObject(i).getString("鄉鎮市區").equals(args[1]) 
						&& jsonRealPrice.getJSONObject(i).getString("土地區段位置或建物區門牌").contains(args[2])
						&& listedYear.substring(0, 3).equals(comparedYear))
					{
						count++;
						amount += jsonRealPrice.getJSONObject(i).getInt("總價元");
						/* System.out.println(jsonRealPrice.getJSONObject(i).getString("鄉鎮市區") + "    " + 
								jsonRealPrice.getJSONObject(i).getString("土地區段位置或建物區門牌") + "    " + 
								jsonRealPrice.getJSONObject(i).getInt("交易年月") + "    " +
								jsonRealPrice.getJSONObject(i).getInt("總價元")); */
					}
				}
			}
		} catch (IOException e) {
			// TODO Auto-generated catch block
			e.printStackTrace();
		}
		avg_price = amount/count;
		System.out.println(avg_price);
	}

}
