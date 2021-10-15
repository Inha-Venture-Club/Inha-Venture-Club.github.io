---
layout: main
main: true
title: About
---

<div class="loading-animation">
    <div class="about">
        <div class="section">
            <div class="title index">01</div>
            <div class="content">
                <h1 class="subtitle">인하벤처클럽</h1>
                <div class="divider"></div>
                <p>
                    인하벤처클럽은 산학 협력단 소속의 창업동아리로 시작하여 실제 창업을 진행하고 각종 창업 공모전에 출전 및 입상하며 기업 공모전, 대외 활동 등 여러 방면에서 두각을 드러내고 있습니다. 수상경력, 개인의 능력은 중요하지 않습니다. 도전 정신과 열정, 동아리에 대한 애정, 사람 사이의 정 그것으로 충분합니다. 인하벤처클럽에 들어와 새로운 도전과 경험으로 자신의 가치와 능력을 발견하여 함께 성장하고 싶습니다. 그런 사람들이 모인 곳이 바로 "인하벤처클럽"입니다.
                </p>
            </div>
        </div>
        <div class="section">
            <div class="title index">02</div>
            <div class="content">
                <h1 class="subtitle">연혁</h1>
                <div class="divider"></div>
                <p>인하벤처클럽은 1997년 5월 25일, 대한민국 벤처기업 1호 비트 컴퓨터 조현정 회장님에 의해 설립되었습니다.</p>
                <div class="historyset" style="text-align:center;">
                    <!-- img slider (https://codepen.io/wlgp73/pen/jOPegpB)-->
                    <script src="https://cdnjs.cloudflare.com/ajax/libs/jquery/3.4.1/jquery.min.js"></script>
                    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/lightbox2/2.11.1/css/lightbox.min.css">
                    <script src="https://cdnjs.cloudflare.com/ajax/libs/lightbox2/2.11.1/js/lightbox.min.js"></script>
                    {% assign history = site.data.history %}
                    {% for item in history %}
                    <div class="history" style="float:left;">
                        <a href="{{item.path}}" data-lightbox="history"><img src="{{item.path}}" alt="" style="width:300px;"></a>
                    </div> 
                    {% endfor %}
                    <!-- END: img slider -->
                </div>
            </div>
        </div>
        <div class="section">
            <div class="title index">03</div>
            <div class="content">
                <h1 class="subtitle">활동</h1>
                <div class="divider"></div>
                <div class="content">
                    {% assign activities = site.data.activities %}
                    <div class="catalogue">
                        {% for activity in activities %}
                        <div class="catalogue-item">
                            <div class="catalogue-title transition">
                                <div class="content-wrap">
                                    <div class="name">{{activity.name}}</div>
                                    <div class="description">{{activity.title}}</div>
                                </div>
                                <div class="icon"><div></div></div>
                            </div>
                            <div class="catalogue-body">
                                {% for subactivity in activity.subactivities %}
                                <div class="item">
                                    <div class="title">{{subactivity.subtitle}}</div>
                                    <ul class="requirement">
                                        {% for explanation in subactivity.explanation %}
                                        <li>{{explanation}}</li>
                                        {% endfor %}
                                        {% if subactivity.Relevant.size > -1 %}
                                            <li>관련자료</li>
                                                <ul>
                                                    {% for Relevant in subactivity.Relevant %}
                                                    <li>{{Relevant.title}} {% if Relevant.url.size > -1 %}<a href="{{Relevant.url}}" style="color:lightgrey;">(바로가기)</a>{% endif %}</li>
                                                    {% endfor %}
                                                </ul>
                                        {% endif %}
                                    </ul>
                                </div>
                                {% endfor %}
                            </div>
                        </div>
                        {% endfor %}
                    </div>
                </div>
            </div>
        </div>
        <div class="section">
            <div class="title index">04</div>
            <div class="content">
                <h1 class="subtitle">관리자 소개</h1>
                <div class="divider"></div>
                <div class="group">
                    <div class="group-name">기술블로그 관리자</div>
                    <ul class="member">
                        {% assign members = site.data.members | where_exp: 'member', 'member.drop != true' | sort: 'id' %} <!--  | where: 'group', 'leader' -->
                        {% for member in members %}
                            {% include about-member.html %}
                        {% endfor %}
                    </ul>
                </div>
            </div>
        </div>
        <!--
        <div class="section">
            <div class="title index">05</div>
            <div class="content">
                <h1 class="subtitle">그 외</h1>
                <ul class="environment">
                    <li></li>
                </ul>
            </div>
        </div>
        -->
    </div>
</div>

<script>
    $('.catalogue-title').click(function() {
        if ($(this).parent().hasClass('visible')) {
            $(this).parent().removeClass('visible');
        } else {
            $(this).parent().addClass('visible');
        }
    });
</script>