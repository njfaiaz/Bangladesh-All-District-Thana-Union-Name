01 Step : DatabaseSeeder.php


<?php
namespace Database\Seeders;
// use Illuminate\Database\Console\Seeds\WithoutModelEvents;
use Illuminate\Database\Seeder;

class DatabaseSeeder extends Seeder
{
    public function run(): void
    {
        $this->call([
            DistrictSeeder::class,
            ThanaSeeder::class,
            UnionsSeeder::class,
        ]);
    }
}

![image](https://github.com/user-attachments/assets/76684343-1b85-4e13-beb4-a1559f0ef4d6)
![image](https://github.com/user-attachments/assets/ace4d454-612d-4248-9b5e-57210a55fc8b)


Data Table Shwo Code 
 @foreach ($addresses as $addressIndex => $address)
                                            @foreach ($address->thanas as $thanaIndex => $thana)
                                                @foreach ($thana->unions as $unionIndex => $union)
                                                    <tr>
                                                        <td>{{ $loop->iteration }}</td>
                                                        <td>{{ $thanaIndex === 0 && $unionIndex === 0 ? $address->district_name : $address->district_name }}
                                                        </td>
                                                        <td>{{ $unionIndex === 0 ? $thana->thana_name : $thana->thana_name }}
                                                        </td>
                                                        <td>{{ $union->union_name }}</td>
                                                    </tr>
                                                @endforeach
                                            @endforeach
                                        @endforeach
