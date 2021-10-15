---
layout: main
main: true
recruit: true
title: 채용정보
---

<div class="loading-animation">
    <div class="recruit">
        <div class="section want">
            <div class="title">인하벤처클럽은 이런 분을 모시고 싶어요</div>
             <div class="content">
                <ul>
                    <li>창업에 열정과 관심을 가지고 있는 누구나</li>
                    <li>본인의 뛰어난 역량을 마음껏 펼치고 싶은 누구나</li>
                    <li>창업에 관심이 있는 다양한 사람들을 만나고싶은 누구나</li>
                    <li>학년, 나이, 전공, 능력 제한없음</li>
                </ul>
            </div>
        </div>
        <div class="section process">
            <div class="title">모집 프로세스</div>
            <div class="content">
                <div class="list">
                    {% for process in site.data.recruit-process %}
                    <div class="process-item">
                        <div class="circle {% if process.detail != nil %}has-detail{% endif %}">
                            <div class="text-wrapper">
                                <div class="index">0{{process.index}}</div>
                                <div class="label">{{process.label}}</div>
                                {% if process.detail != nil %}
                                <ul class="detail">
                                    {% for detail in process.detail %}
                                    <li>{{ detail }}</li>                            
                                    {% endfor %}
                                </ul>
                                {% endif %}
                            </div>
                        </div>
                        <div class="description">
                            {{process.description}}
                        </div>
                    </div>
                    {% endfor %}
                </div>
            </div>
        </div>
        <div class="section welfare culture">
            <div class="title">인하벤처클럽의 문화</div>
            <div class="content">
                <div class="card-list">
                    {% for welfare in site.data.welfares %}
                    {% if welfare.type == 'culture' %}
                    <div class="card">
                        <div class="title">
                            <span class="emoji">{{welfare.emoji}}</span>
                            {{welfare.title}}
                        </div>
                        <div class="subtitle">{{welfare.subtitle}}</div>
                        <div class="description">
                            <ul>
                                {% for description in welfare.description %}
                                <li class="item">{{description}}</li>
                                {% endfor %}
                            </ul>
                        </div>
                    </div>
                    {% endif %}
                    {% endfor %}   
                </div>  
            </div>
        </div>
        <div class="section welfare">
            <div class="title">인하벤처클럽 복지제도</div>
            <div class="content">
                <div class="card-list">
                    {% for welfare in site.data.welfares %}
                    {% if welfare.type == 'welfare' %}
                    <div class="card">
                        <div class="title">
                            <span class="emoji">{{welfare.emoji}}</span>
                            {{welfare.title}}
                        </div>
                        <div class="subtitle">{{welfare.subtitle}}</div>
                        <div class="description">
                            <ul>
                                {% for description in welfare.description %}
                                <li class="item">{{description}}</li>
                                {% endfor %}
                            </ul>
                        </div>
                    </div>
                    {% endif %}
                    {% endfor %}   
                </div>  
            </div>
        </div>
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

