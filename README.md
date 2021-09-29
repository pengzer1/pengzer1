![header](https://capsule-render.vercel.app/api?type=soft&color=auto&height=150&section=header&text=Minjae&fontSize=70&animation=twinkling)

I'm Minjae, computer engineering student. :smile:

* **[Unity first Practice](https://github.com/pengzer1/unity/tree/main/first)**: ~ 2021.07. 
* **Gamejam**: 2021.09.24 ~ 2021.09.26

[![Solved.ac Profile](http://mazassumnida.wtf/api/v2/generate_badge?boj=pega0922)](https://solved.ac/pega0922/)


def normalize_data(n_cases, n_people, scale):
    # TODO: Calculate the number of cases per its population
    norm_cases = []
    for idx, n in enumerate(n_cases):
        norm_cases.append(n * scale / n_people[idx])
    return norm_cases

regions  = ['Seoul', 'Gyeongi', 'Busan', 'Gyeongnam', 'Incheon', 'Gyeongbuk', 'Daegu', 'Chungnam', 'Jeonnam', 'Jeonbuk', 'Chungbuk', 'Gangwon', 'Daejeon', 'Gwangju', 'Ulsan', 'Jeju', 'Sejong']
n_people = [9550227,  13530519, 3359527,     3322373,   2938429,     2630254, 2393626,    2118183,   1838353,   1792476,    1597179,   1536270,   1454679,   1441970, 1124459, 675883,   365309] # 2021-08
n_covid  = [    644,       529,      38,          29,       148,          28,      41,         62,        23,        27,         27,        33,        16,        40,      20,      5,        4] # 2021-09-21

sum_people = sum(n_people) # TODO: The total number of people
sum_covid  = sum(n_covid) # TODO: The total number of new cases
norm_covid = normalize_data(n_covid, n_people, 1000000) # The new cases per 1 million people

# Print population by region
print('### Korean Population by Region')
print('* Total population:', sum_people)
print('| Region | Population | Ratio (%) |')
print('| ------ | ---------- | --------- |')
for idx, pop in enumerate(n_people):
    ratio = pop * 100 / sum_people # TODO: The ratio of new cases to the total
    print('| %s | %d | %.1f |' % (regions[idx], pop, ratio))
print('* Total new case:', sum_covid)
print('| Region | New cases | Ratio (%) | New Cases / 1M |')
print('| ------ | --------- | --------- | -------------- |')
for idx2, pop2 in enumerate(n_covid):
    ratio2 = pop2 * 100 / sum_covid
    print('| %s | %d | %.1f | %.1f |' % (regions[idx2], pop2, ratio2, norm_covid[idx2]))
    
# TODO: Print COVID-19 new cases by region
